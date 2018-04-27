<template>
  <div id="tablearea">
    <table>
      <tr>
        <td><input type="radio"></td>
        <td>#</td>
        <td>Title</td>
        <td>Label</td>
        <td>Artist</td>
        <td>UPC</td>
        <td>Ingestion</td>
        <td>Release Date</td>
      </tr>
      <tr v-for="data in testJson.results" v-bind:key="data.id">
        <td><input type="radio"></td>
        <td>{{ data.id }}</td>
        <td>
          <a href="#modal1" data-toggle="modal" data-target="#modal1">{{ data.title }}</a>
          <div class="modal fade" id="modal1" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
            <div class="modal-dialog" role="document">
              <div class="modal-content">
                <div class="modal-header">
                  <h5 class="modal-title" id="title">Edit Release</h5>
                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                      <span aria-hidden="true">&times;</span>
                    </button>
                </div>
                <div class="modal-body">
                  <div class="modal-body-item">
                    <span class="item-name">Licensor</span>
                    <span class="licensor-name">{{ data.licensor.name }}</span>
                    <button type="button" class="modal-body-btn btn btn-primary">Edit</button>
                  </div>
                  <div class="modal-body-item">
                    <span class="item-name">Title</span>
                    <input type="text">
                  </div>
                  <div class="modal-body-item">
                    <span class="item-name">Title (Local)</span>
                    <input type="text">
                  </div>
                  <div class="modal-body-item">
                    <span class="item-name">Release date</span>
                    <Datepicker></Datepicker>
                  </div>
                </div>
                <div class="modal-footer">
                  <button type="button" class="btn btn-danger">Remove Release</button>
                  <button type="button" class="btn btn-primary">Update Release</button>
                </div>
              </div>
            </div>
          </div>
        </td>
        <td>{{ data.licensor.labels[0].name }}</td>
        <td>{{ data.artist_credit.name }}</td>
        <td>{{ data.serialnumber_set[0].value }}</td>
        <td><span class="badge">{{ data.ingestion_status }}</span></td>
        <td>{{ data.release_date }}</td>
      </tr>
    </table>
  </div>
  
</template>

<style scoped>
table {
  width: 96%;
  margin-left: 2%;
  margin-right: 2%;
  background-color: #fff;
}

td {
  border: 1px solid lightgray;
}

.modal-body-item {
  width: 100%;
  height: 40px;
  float: left;
  margin-bottom: 20px;
}

.modal-body-item:nth-child(1) {
  margin-top: 20px;
}

.item-name {
  font-weight: 500;
  font-size: 20px;
  margin-top: 10px;
  margin-bottom: 10px;
}

.licensor-name {
  margin-left: 60px;
}

.modal-body-btn {
  float: right;
}

.modal-body-item input {
  width: 330px;
  float: right;
}

.vdp-datepicker {
  width: 330px;
  float: right;
}
</style>

<script>
import json from '../../test.json';
import Datepicker from 'vuejs-datepicker';

export default {
  components: {
    Datepicker
  },
  data: function() {
    return {
      testJson: json
    };
  }
};
</script>
