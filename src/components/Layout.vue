<template>
  <div>
    <div class="root-element">

      <div class="unscroll-container">
        <p>But I must explain to you how all this mistaken idea of denouncing pleasure and praising pain was born and I will give you a complete account of the system, and expound the actual teachings of the great explorer of the truth, the master-builder of human happiness. No one rejects, dislikes, or avoids pleasure itself, because it is pleasure, but because those who do not know how to pursue pleasure rationally encounter consequences that are extremely painful. Nor again is there anyone who loves or pursues or desires to obtain pain of itself, because it is pain, but because occasionally circumstances occur in which toil and pain can procure him some great pleasure. To take a trivial example, which of us ever undertakes laborious physical exercise, except to obtain some advantage from it? But who has any right to find fault with a man who chooses to enjoy a pleasure that has no annoying consequences, or one who avoids a pain that produces no resultant pleasure?</p>
        <p>At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.</p>
      </div>

      <Table :sticky-header="stickyHeader" :observer="observer"></Table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Layout',
  components: {
    Table: () => import("./Table")
  },
  data() {
    return {
      observer: null,
      stickyHeader: false,
      viewportHeight: 0
    }
  },
  mounted() {
    this.viewportHeight = Math.max(document.documentElement.clientHeight || 0, window.innerHeight || 0);
    let style = document.createElement('style');
    style.innerHTML = '.b-table-sticky-header { max-height: ' + this.viewportHeight + 'px !important; }';
    document.getElementsByTagName('head')[0].appendChild(style);

    this.observer = new IntersectionObserver(
        this.onElementObserved,
        {
          root: null,
          threshold: 0.1,
        }
    );
    this.observer.observe(document.querySelector('.unscroll-container'));
  },
  beforeDestroy() {
    this.observer.disconnect();
  },
  methods: {
    onElementObserved(entries) {
      entries.forEach(({ target, isIntersecting}) => {

        if( target.classList.contains('unscroll-container') && !isIntersecting) {
          this.__hideTopBlock();
        }

        if( target.classList.contains('fake-row') && isIntersecting ) {
          this.__showTopBlock();
        }

      });
    },
    __hideTopBlock() {
      document.querySelector('.unscroll-container').classList.add('hidden');
      this.stickyHeader = true;
    },
    __showTopBlock() {
      document.querySelector('.unscroll-container').classList.remove('hidden');
      this.stickyHeader = false;
    }
  }
}
</script>

<style lang="scss">
.unscroll-container
{
  overflow: hidden;
  max-height: 1000px;
  transition: max-height 1s ease-in;

  &.hidden
  {
    max-height: 0;
    transition-duration: 0s;
  }
}
</style>
