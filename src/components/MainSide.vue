<script>
import LineChart from '../components/LineChart.vue'

export default {
  components: { LineChart },
  data() {
    return {
      recentTransactions: [
        { image: "person-circle", desc: "Bitcoin Transactions", date: "Jan 16, 2020", number: "45242", amount: "-$853.00", status: "success" },
        { image: "person-circle", desc: "Sent to anitonia", date: "Jan 16, 2020", number: "87212", amount: "-$153.00", status: "pending" },
        { image: "person-circle", desc: "Withdraw Paypal", date: "Jan 16, 2020", number: "36275", amount: "-$153.00", status: "success" },
      ],
      recentContacts: [
        { img: "img1.jpg" },
        { img: "img2.jpg" },
        { img: "img3.jpg" },
        { img: "img4.jpg" },
        { img: "img6.jpg" },
      ],
      people: [
        { img: "img1.jpg" },
        { img: "img2.jpg" },
        { img: "img3.jpg" }
      ],
      flags: [
        { img: "img7.jpg" },
        { img: "img7.jpg" }
      ],
    }
  },
  methods: {
    getImageUrl: function (name) {
      return new URL(`../assets/images/${name}`, import.meta.url).href
    }
  }
}
</script>

<template>
  <div class="column pt-5">
    <div class="navbar-end">
      <div class="navbar-item p-0">
        <div class="is-flex is-align-items-center is-size-4">
          <i class="bi bi-search pr-5" style="color: #C1C1C1;"></i>
          <i class="bi bi-bell pr-5" style="color: #C1C1C1;"></i>
          <img class="image is-32x32 recipientImg" src="../assets/images/img7.jpg" alt="Contact Image">
        </div>
      </div>
    </div>
  </div>

  <div class="column">
    <p class="is-size-5 has-text-weight-bold">My Card</p>
  </div>

  <div class="columns">
    <!-- <div class="fw-bold"> -->
    <div class="column is-one-third-tablet is-one-quarter-desktop p-5">
      <div class="cardImg">
        <div>
          <p class="cardImg-label">Name</p>
          <p class="cardImg-name">Carla Rosser</p>
        </div>

        <div>
          <div class="is-flex is-justify-content-space-between is-align-items-center">
            <p class="cardImg-number">1200 01452 54215</p>
            <p><img src="../assets/visa.svg" alt=""></p>
          </div>
          <p class="cardImg-number">08/23</p>
        </div>
      </div>

      <!-- Send Money -->

      <div>
        <p class="is-size-5 has-text-weight-bold mt-3">Send Money</p>

        <div class="card my-5 cardOption">
          <div class="card-content p-4">
            <div class="content is-flex is-justify-content-space-between">
              <img src="../assets/mastercard.svg" alt="mastercard logo">
              <span>Debit</span>
              <span><i class="bi bi-currency-dollar"></i>10.680</span>
              <i class="bi bi-chevron-down"></i>
            </div>
          </div>
        </div>

        <div class="card my-5 px-4 py-2">
          <p class="mb-0 is-flex is-align-items-center">
            <img class="image is-16x16 recipientImg" src="../assets/images/img4.jpg" alt="Recipient Image">
            <span class="pl-2">Enter the amount</span>
          </p>
          <!-- <div class="card-content"> -->
          <div class="content is-flex is-justify-content-space-between is-align-items-center">
            <i class="bi bi-currency-dollar is-flex is-justify-content-center"></i>
            <input class="input amtInput is-size-5 px-0" type="text" placeholder="800.00">
            <span class="is-flex px-2 flags">
              <img class="image is-16x16 recipientImg overlapImg" v-for="(flag, index) in flags" :key="index"
                :src="getImageUrl(flag.img)" alt="Flag Image">
            </span>
          </div>
        </div>

        <div class="my-5 py-4 is-flex is-justify-content-space-between">
          <p class="is-flex">
            <img class="image is-24x24 recipientImg" src="../assets/images/img2.jpg" alt="Recipient Image">
            <span class="pl-2">Astrid Hayes</span>
          </p>
          <span class="tag is-rounded" style="background-color: #DFF3FE;"><i class="bi bi-plus-lg"
              style="color: #0177FB;"></i></span>
        </div>

        <div class="my-5">
          <button class="button is-fullwidth py-5 sendBtn">Send Money</button>
        </div>

        <div class="transfer my-5 p-4 is-shadowless">
          <div class="content">
            <p>Quick Transfer</p>

            <div class="card my-3 p-3">
              <div class="content is-flex is-justify-content-space-between">
                <span class="is-flex">
                  <img src="../assets/mastercard.svg" alt="">
                  <span class="pl-1">Debit</span>
                </span>
                <span class="is-flex">
                  <span class="pr-1">$10,432</span>
                  <i class="bi bi-chevron-down"></i>
                </span>
              </div>
            </div>

            <div class="card my-5 p-2">
              <p class="mb-0">
                <span class="pl-1">Enter the amount</span>
              </p>
              <p class="content is-flex is-justify-content-space-between is-align-items-center px-2">
                <i class="bi bi-currency-dollar is-flex is-justify-content-center"></i>
                <input class="input amtInput is-size-5 px-0" type="text" placeholder="800.00">
                <img class="image is-16x16 recipientImg" v-for="(flag, index) in flags" :key="index"
                  :src="getImageUrl(flag.img)" alt="Flag Image">
              </p>
            </div>
            <div class="my-3 is-flex is-justify-content-space-between is-align-items-center options-text">
              <span class="has-text-centered">
                <span class="is-flex is-justify-content-center p-3 options"><img src="../assets/camSend.svg"
                    alt="send"></span><br>
                <span>Send</span>
              </span>
              <span class="has-text-centered">
                <span class="is-flex is-justify-content-center p-3 options"><img src="../assets/camReceive.svg"
                    alt="receive"></span><br>
                <span>Recieve</span>
              </span>
              <span class="has-text-centered">
                <span class="is-flex is-justify-content-center p-3 options"><img src="../assets/invoiceYellow.svg"
                    alt="invoicing"></span><br>
                <span>Invoicing</span>
              </span>
              <span class="has-text-centered">
                <span class="is-flex is-justify-content-center p-3 options"><img src="../assets/more.svg"
                    alt="more"></span><br>
                <span>More</span>
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>



    <div class="column px-5">
      <div class="columns m-0">
        <div class="column">
          <div class="is-flex is-justify-content-space-between is-align-items-center pr-6 mb-5">
            <p>Money Flow</p>
            <p class="is-flex is-align-items-center">
              <img class="px-2" src="../assets/progress_grey.svg" alt="progress">
              <img class="px-2" src="../assets/bars_filled.svg" alt="progress">
            </p>
          </div>
          <div class="is-flex is-justify-content-space-between is-align-items-center pr-6">
            <div class="is-flex">
              <p class="">
                <img src="../assets/progress_circle.svg" alt="progress">
                <span class="px-3">Savings</span>
              </p>
              <p>
                <img src="../assets/progress.svg" alt="progress">
                <span class="px-3">+6,79%</span>
              </p>
            </div>
            <div>
              <div class="dropdown">
                <div class="dropdown-trigger">
                  <button class="button" aria-haspopup="true" aria-controls="dropdown-menu">
                    <span>Week</span>
                    <span class="icon is-small">
                      <i class="bi bi-chevron-down"></i>
                    </span>
                  </button>
                </div>
                <div class="dropdown-menu" id="dropdown-menu" role="menu">
                  <div class="dropdown-content">
                    <a href="#" class="dropdown-item">
                      Year
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Line Chart -->
          <div class="container">
            <LineChart />
          </div>
        </div>
        <div class="column is-one-third px-0 ">
          <div class="mb-5">
            <div class="is-flex is-justify-content-space-between">
              <p>Recent Contacts</p>
              <p>
                <i class="bi bi-pencil pr-5" style="color: #BCCDE1;"></i>
                <i class="bi bi-search" style="color: #0276FD;"></i>
              </p>
            </div>
            <p>18 recipients</p>
          </div>

          <div class="is-flex is-justify-content-space-between is-align-items-center pb-5">
            <img class="image is-32x32 recipientImg" v-for="(contact, index) in recentContacts" :key="index"
              :src="getImageUrl(contact.img)" alt="Contact Image">
            <i class="bi bi-chevron-right"></i>
          </div>

          <div class="mt-5 groupParty">
            <div class="content p-5 groupParty-card">
              <p><span class="text-gray">Group </span>Party</p>
              <div class="is-flex is-justify-content-space-between is-align-items-center">
                <div class="is-flex">
                  <img class="image is-32x32 recipientImg" v-for="(person, index) in people" :key="index"
                    :src="getImageUrl(person.img)" alt="Contact Image">
                </div>
                <div><span class="groupParty-num">+5</span></div>
                <i class="bi bi-chat is-size-6"></i>
              </div>

              <div class="is-flex is-justify-content-space-between is-align-items-center mt-3 pt-5">
                <span class="is-flex is-align-items-center">
                  <span><img class="image is-48x48 recipientImg" src="../assets/images/img1.jpg" alt="A person"></span>
                  <span class="pl-3">
                    <span>Dakota Milk</span><br>
                    <span>$ 420.00</span>
                  </span>
                </span>
                <i class="bi bi-chevron-right is-size-6"></i>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="pt-5">
        <div class="is-flex is-justify-content-space-between">
          <p class="has-text-weight-bold">Recent Transactions</p>
          <a href="#">
            <span>View all</span>
            <span class="icon is-small">
              <i class="bi bi-chevron-right"></i>
            </span>
          </a>
        </div>

        <div class="table-container pt-5">
          <table class="table is-fullwidth">
            <tbody>
              <tr v-for="(transaction, index) in recentTransactions" :key="index">
                <td>
                  <img class="image is-32x32 recipientImg" src="../assets/images/img1.jpg" alt="Recipient Image">
                </td>
                <td>{{ transaction.desc }}</td>
                <td>{{ transaction.date }}</td>
                <td>*****{{ transaction.number }}</td>
                <td>{{ transaction.amount }}</td>
                <td><span class="status" :class="transaction.status">{{ transaction.status }}</span></td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="pt-5">
        <div class="card">
          <div class="card-content">
            <p class="pb-5 has-text-weight-bold">Statistics</p>

            <div class="columns is-mobile is-multiline py-5">
              <div class="column is-flex">
                <span class="stats-img p-4 bg-purple image is-48x48 is-flex">
                  <img class="" src="../assets/customers.svg" alt="customers">
                </span>
                <span class="ml-2">
                  <span>220k</span><br>
                  <span class="text-gray">Customers</span>
                </span>
              </div>
              <div class="column is-flex">
                <span class="stats-img p-4 bg-blue image is-48x48 is-flex">
                  <img class="" src="../assets/remittance.svg" alt="customers">
                </span>
                <span class="ml-2">
                  <span>230k</span><br>
                  <span class="text-gray">Remittance</span>
                </span>
              </div>
              <div class="column is-flex">
                <span class="stats-img p-4 bg-green image is-48x48 is-flex">
                  <img class="" src="../assets/donation.svg" alt="customers">
                </span>
                <span class="ml-2">
                  <span>270k</span><br>
                  <span class="text-gray">Donation</span>
                </span>
              </div>
              <div class="column is-flex">
                <span class="stats-img p-4 bg-yellow image is-48x48 is-flex">
                  <img class="" src="../assets/watchtime.svg" alt="customers">
                </span>
                <span class="ml-2">
                  <span>130k</span><br>
                  <span class="text-gray">Watchtime</span>
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.cardImg {
  padding: 11px 18px 7px 15px;
  height: 15vh;
  background-image: url('../assets/cardBg.svg');
  background-repeat: no-repeat;
  background-color: #0177FB;
  background-size: cover;
  border-radius: 11.7px;
  color: white;
  display: flex;
  justify-content: space-between;
  flex-direction: column;

  &-label {
    font-size: 9px;
    line-height: 10px;
    font-weight: bold;
  }

  &-name {
    font-size: 13px;
    line-height: 15px;
    font-weight: bold;
  }

  &-number {
    font-size: 10px;
    line-height: 12px;
    font-weight: bold;
  }
}

.amtInput {
  border: none;
  box-shadow: none !important;
}

.transfer {
  border: 0.566969px solid #E8E8E8 !important;
  border-radius: 10px;
  padding: 15px 12px 27px 12px;
}

.table td {
  border: none;
  padding: 20px 10px;
}

.recipientImg {
  border-radius: 50%
}

.overlapImg {
  border: 2px solid white;
}

.sendBtn {
  color: white !important;
  background-color: #0177FB;
  border: none;
  border-radius: 16px;

  &:hover {
    box-shadow: rgba(30, 144, 255, 0.7) 0px 0px 0px 0.125rem;
  }
}

.options {
  border: 0.7px solid #F2F2F2;
  border-radius: 7px;
}

.options-text {
  color: #798BA3;
  font-size: 10px;
}

.groupParty {
  &-card{
    box-shadow: 0px 4px 17px rgba(0, 0, 0, 0.06) !important;
    border-radius: 8px !important;
  }
  &-num {
    height: 26px;
    width: 26px;
    padding: 10px;
    border-radius: 50%;
    border: 0.8px dashed #DDE5F0;
    color: #0176FA;
  }
}

.fw-bold {
  font-weight: 500;
}

.stats-img {
  border-radius: 50%;
}

.bg-purple {
  background-color: #EFECFD;
}

.bg-blue {
  background-color: #E4F8FB;
}

.bg-green {
  background-color: #E5F7ED;
}

.bg-yellow {
  background-color: #FDF1E2;
}

.status {
  padding: 5px 12px;
  border-radius: 4px;
  text-transform: capitalize;
}

.success {
  background: #EBFFF3;
  color: #61BB84;
}

.pending {
  background: #FFF1ED;
  color: #FFAA90;
}

.text-gray {
  color: #7C8CA6;
}
</style>