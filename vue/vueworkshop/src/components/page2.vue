<template >
  <div id="bcolor">
    <div>
      <b-table :items="studentInfo"></b-table>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Page2",
  data() {
    return {
      studentInfo: [],
    };
  },
  mounted() {
    axios
      .get("https://mocki.io/v1/423b4c07-dc19-4a17-94f8-fd8d2b0484b8")
      .then((res) => {
        const info = res.data;
        this.studentInfo = info.filter((info) => [info.includes]);
      });
  },
};
</script>

<style >
#bcolor {
  background-color: rgb(97, 219, 97);
}
</style>