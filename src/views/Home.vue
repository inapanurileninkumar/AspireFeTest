<script>
import { onBeforeMount } from 'vue';
import { routeTo } from '@mixins/helpers';

export default {
  name: 'Home',
  setup () {
    onBeforeMount(() => {
      routeTo('Cards');
    });
  }
};
</script>
