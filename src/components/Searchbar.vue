<template>
  <div id="searchbar">
    <select class="custom-select" id="searchselect">
      <option value="5">5</option>
      <option value="10">10</option>
      <option value="15">15</option>
      <option value="30">30</option>
      <option value="50">50</option>
      <option value="100">100</option>
    </select>
    <div id="textbox">
      <input type="text" id="textarea" class="form-control" placeholder="Type text" aria-placeholder="Type text">
      <button type="button" class="btn btn-primary" id="searchbtn" @click="getData">search</button>
    </div>
  </div>
</template>

<style scoped>
#searchbar {
  width: 96%;
  height: 70px;
  background-color: #0082f4;
  margin-top: 2%;
  margin-left: 2%;
  margin-right: 2%;
}

#searchselect {
  width: 7%;
  height: 50px;
  margin-left: 10px;
  margin-top: 10px;
  margin-bottom: 10px;
  float: left;
}

#textbox {
  float: left;
  width: 90%;
  height: 50px;
  margin-top: 10px;
  margin-bottom: 10px;
  margin-left: 10px;
  background-color: #fff;
  border-radius: 5px 5px 5px 5px;
}

#textarea {
  width: 90%;
  float: left;
  height: 40px;
  margin-top: 5px;
  margin-bottom: 5px;
  border: none;
}

#searchbtn {
  height: 40px;
  float: right;
  margin-top: 5px;
  margin-bottom: 5px;
  margin-right: 5px;
}
</style>

<script>
import axios from 'axios';
export default {
  data: function() {
    return {
      datas: [],
      errors: []
    };
  },
  methods: {
    getData: function() {
      axios
        .get('/data')
        .then(res => {
          console.log(response);
        })
        .catch(err => alert('데이터를 찾을 수 없습니다.' + err.response));
    }
  }
};
</script>
