<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-xl-3 col-md-6 center">
          <stats-card>
            <div slot="header" class="icon-dnager">
              <i class="nc-icon nc-alien-33 text-danger"></i>
            </div>
            <div slot="content">
              <p class="card-category">Alerts</p>
              <h4 class="card-title">105</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-refresh"></i>Updated now
            </div>
          </stats-card>
        </div>

        <div class="col-xl-3 col-md-6 center">
          <stats-card>
            <div slot="header" class="icon-success">
              <i class="nc-icon nc-notes text-success"></i>
            </div>
            <div slot="content">
              <p class="card-category">Events</p>
              <h4 class="card-title">1345</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-calendar-o"></i>Last day
            </div>
          </stats-card>
        </div>

        <div class="col-xl-3 col-md-6 center">
          <stats-card>
            <div slot="header" class="icon-info">
              <i class="nc-icon nc-favourite-28 text-primary"></i>
            </div>
            <div slot="content">
              <p class="card-category">Avg ETA (ms)</p>
              <h4 class="card-title">23</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-clock-o"></i>Last day
            </div>
          </stats-card>
        </div>
      </div>


      <!-- second row of cards -->
      <div class="row">
        <div class="col-xl-3 col-md-6 center">
          <stats-card>
            <div slot="header" class="icon-warning">
              <i class="nc-icon nc-atom text-warning"></i>
            </div>
            <div slot="content">
              <p class="card-category">Test Cases</p>
              <h4 class="card-title">363</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-refresh"></i>Last day
            </div>
          </stats-card>
        </div>

        <div class="col-xl-3 col-md-6 center">
          <stats-card>
            <div slot="header" class="icon-success">
              <i class="nc-icon nc-light-3 text-success"></i>
            </div>
            <div slot="content">
              <p class="card-category">Epic AC Coverage</p>
              <h4 class="card-title">45%</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-calendar-o"></i>Last day
            </div>
          </stats-card>
        </div>

        <div class="col-xl-3 col-md-6 center">
          <stats-card>
            <div slot="header" class="icon-danger">
              <i class="nc-icon nc-vector text-danger"></i>
            </div>
            <div slot="content">
              <p class="card-category">Issues</p>
              <h4 class="card-title">+45</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-refresh"></i>Updated now
            </div>
          </stats-card>
        </div>
      </div>

      <card>
        <h4 slot="header" class="card-title">Send Event</h4>
        <form>
          <div class="row">
            <div class="col-md-5">




              <base-dropdown tag="div">
                <template slot="title">
                  <base-input type="text"
                            label="Event API"
                            placeholder="Select Event"
                            v-model="selectedValue"
                            >
                  </base-input>
                  <p>Selected Value: {{ selectedValue }}</p>

                  <!-- <span class="notification">???</span> -->
                </template>

                <!-- HOW TO MAKE THESE ATTACH TO selectedValue and populate the input field?? -->

                <span class="dropdown-item"  href="#">Notification 1</span>
                <a class="dropdown-item" value="option1" href="#">Notification 2</a>
                <a class="dropdown-item" href="#">Notification 3</a>
                <a class="dropdown-item" href="#">Notification 4</a>
                <a class="dropdown-item" href="#">Another notification</a>
              </base-dropdown>
            </div>

          </div>



          <div class="row">
            <div class="col-md-12">
              <div class="form-group">
                <label>Event JSON</label>
                <textarea rows="10" class="form-control border-input"
                          placeholder="Here can be your description"
                          >
                  </textarea>
              </div>
            </div>
          </div>
          <div class="text-center">
            <button type="submit" class="btn btn-info btn-fill float-right">
              Publish
            </button>
          </div>
          <div class="clearfix"></div>
        </form>
      </card>

    </div>
  </div>
</template>
<script>
  import ChartCard from 'src/components/Cards/ChartCard.vue'
  import StatsCard from 'src/components/Cards/StatsCard.vue'
  import LTable from 'src/components/Table.vue'

  export default {
    components: {
      LTable,
      ChartCard,
      StatsCard
    },
    data () {
      return {
        selectedValue: '',

        editTooltip: 'Edit Task',
        deleteTooltip: 'Remove',
        pieChart: {
          data: {
            labels: ['40%', '20%', '40%'],
            series: [40, 20, 40]
          }
        },
        lineChart: {
          data: {
            labels: ['9:00AM', '12:00AM', '3:00PM', '6:00PM', '9:00PM', '12:00PM', '3:00AM', '6:00AM'],
            series: [
              [287, 385, 490, 492, 554, 586, 698, 695],
              [67, 152, 143, 240, 287, 335, 435, 437],
              [23, 113, 67, 108, 190, 239, 307, 308]
            ]
          },
          options: {
            low: 0,
            high: 800,
            showArea: false,
            height: '245px',
            axisX: {
              showGrid: false
            },
            lineSmooth: true,
            showLine: true,
            showPoint: true,
            fullWidth: true,
            chartPadding: {
              right: 50
            }
          },
          responsiveOptions: [
            ['screen and (max-width: 640px)', {
              axisX: {
                labelInterpolationFnc (value) {
                  return value[0]
                }
              }
            }]
          ]
        },
        barChart: {
          data: {
            labels: ['Jan', 'Feb', 'Mar', 'Apr', 'Mai', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
            series: [
              [542, 443, 320, 780, 553, 453, 326, 434, 568, 610, 756, 895],
              [412, 243, 280, 580, 453, 353, 300, 364, 368, 410, 636, 695]
            ]
          },
          options: {
            seriesBarDistance: 10,
            axisX: {
              showGrid: false
            },
            height: '245px'
          },
          responsiveOptions: [
            ['screen and (max-width: 640px)', {
              seriesBarDistance: 5,
              axisX: {
                labelInterpolationFnc (value) {
                  return value[0]
                }
              }
            }]
          ]
        },
        tableData: {
          data: [
            {title: 'Sign contract for "What are conference organizers afraid of?"', checked: false},
            {title: 'Lines From Great Russian Literature? Or E-mails From My Boss?', checked: true},
            {
              title: 'Flooded: One year later, assessing what was lost and what was found when a ravaging rain swept through metro Detroit',
              checked: true
            },
            {title: 'Create 4 Invisible User Experiences you Never Knew About', checked: false},
            {title: 'Read "Following makes Medium better"', checked: false},
            {title: 'Unfollow 5 enemies from twitter', checked: false}
          ]
        }
      }
    }
  }
</script>
<style>
.center {
  margin: auto;
}

</style>
