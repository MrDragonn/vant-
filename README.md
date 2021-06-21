<template>
   <van-field
              v-model="durationDay"
              type="digit"
              label="工期(天)"
              placeholder="请填写工期(整数)"
            />

</template>
<script>
onMounted(() => {
      console.log("DMO 挂载");
      var __timer;
      window.onresize = () => {
        console.log(
          "window resize",
          window.screen.height,
          document.body.clientHeight
        );
        var activeElement;
        if (document.activeElement) {
          activeElement = document.activeElement;
        }
        if (window.screen.height - document.body.clientHeight < 150) {
          //收键盘的情况
          console.log("收键盘的情况");
          showBottom.value = true;
          // document.activeElement.blur();
        } else {
          console.log("键盘弹起的情况");
          //键盘弹起的情况
          __timer = window.setTimeout(() => {
            showBottom.value = false;
            if ("scrollIntoView" in activeElement) {
              activeElement.scrollIntoView(false);
            } else {
              activeElement.scrollIntoViewIfNeeded(false);
            }
          }, 0);
        }
      };
    });

</script>
