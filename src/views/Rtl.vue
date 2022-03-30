<template>
  <div class="py-4 container-fluid">
    <div class="row">
      <div class="col-lg-3 col-sm-6 mb-lg-0 mb-4">
        <mini-statistics-card
          title="اموال اليوم"
          value="$53,000"
          :percentage="{
            value: '+55%',
            color: 'text-success',
          }"
          :icon="{
            component: 'ni ni-money-coins',
            background: iconBackground,
          }"
          direction-reverse
        />
      </div>
      <div class="col-lg-3 col-sm-6 mb-lg-0 mb-4">
        <mini-statistics-card
          title="مستخدمو الیوم"
          value="2,300"
          :percentage="{
            value: '+3%',
            color: 'text-success',
          }"
          :icon="{
            component: 'ni ni-world',
            background: iconBackground,
          }"
          direction-reverse
        />
      </div>
      <div class="col-lg-3 col-sm-6 mb-lg-0 mb-4">
        <mini-statistics-card
          title="عملاء جدد"
          value="+3,462"
          :percentage="{
            value: '-2%',
            color: 'text-danger',
          }"
          :icon="{
            component: 'ni ni-paper-diploma',
            background: iconBackground,
          }"
          direction-reverse
        />
      </div>
      <div class="col-lg-3 col-sm-6">
        <mini-statistics-card
          title="مبیعات"
          value="$103,430"
          :percentage="{
            value: '+5%',
            color: 'text-success',
          }"
          :icon="{
            component: 'ni ni-cart',
            background: iconBackground,
          }"
          direction-reverse
        />
      </div>
    </div>
    <div class="row">
      <div class="col-lg-7 mb-lg-0 mb-4">
        <div class="card">
          <div class="card-body p-3">
            <div class="row">
              <div class="col-lg-6 mb-lg-0 mb-4">
                <div class="d-flex flex-column h-100">
                  <p class="mb-1 pt-2 text-bold">بناها المطورون</p>
                  <h5 class="font-weight-bolder">Soft UI Dashboard</h5>
                  <p class="mb-5">
                    من الألوان والبطاقات والطباعة إلى العناصر المعقدة ، ستجد
                    الوثائق الكاملة.
                  </p>
                  <a
                    class="text-dark font-weight-bold ps-1 mb-0 icon-move-left mt-auto"
                    href="javascript:;"
                  >
                    اقرأ المستندات
                    <i
                      class="fas fa-arrow-left text-sm ms-1"
                      aria-hidden="true"
                    ></i>
                  </a>
                </div>
              </div>
              <div class="col-lg-4 me-auto ms-0 text-center">
                <div
                  class="bg-gradient-success border-radius-lg min-height-200"
                >
                  <img
                    src="../assets/img/shapes/waves-white.svg"
                    class="position-absolute h-100 top-0 d-md-block d-none"
                    alt="waves"
                  />
                  <div class="position-relative pt-5 pb-4">
                    <img
                      class="max-width-500 w-100 position-relative z-index-2"
                      src="../assets/img/illustrations/rocket-white.png"
                    />
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-lg-5">
        <div class="card h-100 p-3">
          <div
            class="overflow-hidden position-relative border-radius-lg bg-cover h-100"
            style="
              background-image: url('https://demos.creative-tim.com/soft-ui-dashboard/assets/img/ivancik.jpg');
            "
          >
            <span class="mask bg-gradient-dark"></span>
            <div class="card-body position-relative z-index-1 p-3 h-100">
              <div class="d-flex flex-column h-100">
                <h5 class="text-white font-weight-bolder mb-4 pt-2">
                  العمل مع الصواريخ
                </h5>
                <p class="text-white mb-5">
                  تكوين الثروة هو لعبة تطوري حديثة ذات حصيلة إيجابية. الأمر كله
                  يتعلق بمن يغتنم الفرصة أولاً هذه بطاقة بسيطة.
                </p>
                <a
                  class="text-white font-weight-bold ps-1 mb-0 icon-move-left mt-auto"
                  href="javascript:;"
                >
                  اقرأ المستندات
                  <i
                    class="fas fa-arrow-left text-sm ms-1"
                    aria-hidden="true"
                  ></i>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="mt-4 row">
      <div class="col-lg-5 mb-lg-0 mb-4">
        <div class="card">
          <div class="card-body p-3">
            <reports-bar-chart
              id="chart-bar"
              title="المستخدمين النشطين"
              description="(<strong>+23%</strong>)  من الأسبوع الماضي"
              :chart="{
                labels: [
                  'Apr',
                  'May',
                  'Jun',
                  'Jul',
                  'Aug',
                  'Sep',
                  'Oct',
                  'Nov',
                  'Dec',
                ],
                datasets: {
                  label: 'Sales',
                  data: [450, 200, 100, 220, 500, 100, 400, 230, 500],
                },
              }"
              :items="[
                {
                  icon: {
                    color: 'primary',
                    component: faUsers,
                  },
                  label: 'المستخدمون',
                  progress: { content: '37K', percentage: 60 },
                },
                {
                  icon: { color: 'info', component: faHandPointer },
                  label: ' نقرات',
                  progress: { content: '2m', percentage: 90 },
                },
                {
                  icon: { color: 'warning', component: faCreditCard },
                  label: 'مبيعات',
                  progress: { content: '435$', percentage: 30 },
                },
                {
                  icon: { color: 'danger', component: faScrewdriverWrench },
                  label: 'العناصر',
                  progress: { content: '43', percentage: 50 },
                },
              ]"
            >
            </reports-bar-chart>
          </div>
        </div>
      </div>
      <div class="col-lg-7">
        <gradient-line-chart
          id="chart-line"
          title="نظرة عامة على المبيعات"
          description="<i class='fa fa-arrow-up text-success'></i>
      <span class='font-weight-bold'>4% أكثر</span> في عام 2021"
          :chart="{
            labels: [
              'Apr',
              'May',
              'Jun',
              'Jul',
              'Aug',
              'Sep',
              'Oct',
              'Nov',
              'Dec',
            ],
            datasets: [
              {
                label: 'Mobile Apps',
                data: [50, 40, 300, 220, 500, 250, 400, 230, 500],
              },
              {
                label: 'Websites',
                data: [30, 90, 40, 140, 290, 290, 340, 230, 400],
              },
            ],
          }"
        />
      </div>
    </div>
    <div class="mt-4 row">
      <div class="col-lg-8 col-md-6 mb-md-0 mb-4">
        <div class="card">
          <div class="card-header pb-0">
            <div class="row mb-3">
              <div class="col-6">
                <h6>المشاريع</h6>
                <p class="text-sm">
                  <i class="fa fa-check text-info" aria-hidden="true"></i>
                  <span class="font-weight-bold ms-1">30 انتهى</span> هذا الشهر
                </p>
              </div>
              <div class="col-6 my-auto text-start">
                <div class="dropdown float-start ps-4">
                  <a
                    class="cursor-pointer"
                    id="dropdownTable"
                    data-bs-toggle="dropdown"
                    aria-expanded="false"
                  >
                    <i
                      class="fa fa-ellipsis-v text-secondary"
                      aria-hidden="true"
                    ></i>
                  </a>
                  <ul
                    class="dropdown-menu px-2 py-3 me-n4"
                    aria-labelledby="dropdownTable"
                  >
                    <li>
                      <a
                        class="dropdown-item border-radius-md"
                        href="javascript:;"
                        >عمل</a
                      >
                    </li>
                    <li>
                      <a
                        class="dropdown-item border-radius-md"
                        href="javascript:;"
                        >عمل آخر</a
                      >
                    </li>
                    <li>
                      <a
                        class="dropdown-item border-radius-md"
                        href="javascript:;"
                        >شيء آخر هنا</a
                      >
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
          <div class="card-body p-0 pb-2">
            <div class="table-responsive">
              <table class="table align-items-center mb-0">
                <thead>
                  <tr>
                    <th
                      class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      المشروع
                    </th>
                    <th
                      class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7 ps-2"
                    >
                      أعضاء
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      ميزانية
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      إكمال
                    </th>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <td>
                      <div class="d-flex px-2 py-1">
                        <div>
                          <img
                            src="../assets/img/small-logos/logo-xd.svg"
                            class="avatar avatar-sm ms-3"
                          />
                        </div>
                        <div class="d-flex flex-column justify-content-center">
                          <h6 class="mb-0 text-sm">Soft UI XD الإصدار</h6>
                        </div>
                      </div>
                    </td>
                    <td>
                      <div class="avatar-group mt-2">
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Ryan Tompson"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-1.jpg"
                          />
                        </a>
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Romina Hadid"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-2.jpg"
                          />
                        </a>
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Alexander Smith"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-3.jpg"
                          />
                        </a>
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Jessica Doe"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-4.jpg"
                          />
                        </a>
                      </div>
                    </td>
                    <td class="align-middle text-center text-sm">
                      <span class="text-xs font-weight-bold">$14,000</span>
                    </td>
                    <td class="align-middle">
                      <div class="progress-wrapper w-75 mx-auto">
                        <div class="progress-info">
                          <div class="progress-percentage">
                            <span class="text-xs font-weight-bold">60%</span>
                          </div>
                        </div>
                        <div class="progress">
                          <div
                            class="progress-bar bg-gradient-info w-60"
                            role="progressbar"
                            aria-valuenow="60"
                            aria-valuemin="0"
                            aria-valuemax="100"
                          ></div>
                        </div>
                      </div>
                    </td>
                  </tr>
                  <tr>
                    <td>
                      <div class="d-flex px-2 py-1">
                        <div>
                          <img
                            src="../assets/img/small-logos/logo-atlassian.svg"
                            class="avatar avatar-sm ms-3"
                          />
                        </div>
                        <div class="d-flex flex-column justify-content-center">
                          <h6 class="mb-0 text-sm">
                            أضف مسار التقدم إلى التطبيق الداخلي
                          </h6>
                        </div>
                      </div>
                    </td>
                    <td>
                      <div class="avatar-group mt-2">
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Romina Hadid"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-2.jpg"
                          />
                        </a>
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Jessica Doe"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-4.jpg"
                          />
                        </a>
                      </div>
                    </td>
                    <td class="align-middle text-center text-sm">
                      <span class="text-xs font-weight-bold">$3,000</span>
                    </td>
                    <td class="align-middle">
                      <div class="progress-wrapper w-75 mx-auto">
                        <div class="progress-info">
                          <div class="progress-percentage">
                            <span class="text-xs font-weight-bold">10%</span>
                          </div>
                        </div>
                        <div class="progress">
                          <div
                            class="progress-bar bg-gradient-info w-10"
                            role="progressbar"
                            aria-valuenow="10"
                            aria-valuemin="0"
                            aria-valuemax="100"
                          ></div>
                        </div>
                      </div>
                    </td>
                  </tr>
                  <tr>
                    <td>
                      <div class="d-flex px-2 py-1">
                        <div>
                          <img
                            src="../assets/img/small-logos/logo-slack.svg"
                            class="avatar avatar-sm ms-3"
                          />
                        </div>
                        <div class="d-flex flex-column justify-content-center">
                          <h6 class="mb-0 text-sm">
                            إصلاح أخطاء النظام الأساسي
                          </h6>
                        </div>
                      </div>
                    </td>
                    <td>
                      <div class="avatar-group mt-2">
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Romina Hadid"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-3.jpg"
                          />
                        </a>
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Jessica Doe"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-1.jpg"
                          />
                        </a>
                      </div>
                    </td>
                    <td class="align-middle text-center text-sm">
                      <span class="text-xs font-weight-bold">غير مضبوط</span>
                    </td>
                    <td class="align-middle">
                      <div class="progress-wrapper w-75 mx-auto">
                        <div class="progress-info">
                          <div class="progress-percentage">
                            <span class="text-xs font-weight-bold">100%</span>
                          </div>
                        </div>
                        <div class="progress">
                          <div
                            class="progress-bar bg-gradient-success w-100"
                            role="progressbar"
                            aria-valuenow="100"
                            aria-valuemin="0"
                            aria-valuemax="100"
                          ></div>
                        </div>
                      </div>
                    </td>
                  </tr>
                  <tr>
                    <td>
                      <div class="d-flex px-2 py-1">
                        <div>
                          <img
                            src="../assets/img/small-logos/logo-spotify.svg"
                            class="avatar avatar-sm ms-3"
                          />
                        </div>
                        <div class="d-flex flex-column justify-content-center">
                          <h6 class="mb-0 text-sm">
                            إطلاق تطبيق الهاتف المحمول الخاص بنا
                          </h6>
                        </div>
                      </div>
                    </td>
                    <td>
                      <div class="avatar-group mt-2">
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Ryan Tompson"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-4.jpg"
                          />
                        </a>
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Romina Hadid"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-3.jpg"
                          />
                        </a>
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Alexander Smith"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-4.jpg"
                          />
                        </a>
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Jessica Doe"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-1.jpg"
                          />
                        </a>
                      </div>
                    </td>
                    <td class="align-middle text-center text-sm">
                      <span class="text-xs font-weight-bold">$20,500</span>
                    </td>
                    <td class="align-middle">
                      <div class="progress-wrapper w-75 mx-auto">
                        <div class="progress-info">
                          <div class="progress-percentage">
                            <span class="text-xs font-weight-bold">100%</span>
                          </div>
                        </div>
                        <div class="progress">
                          <div
                            class="progress-bar bg-gradient-success w-100"
                            role="progressbar"
                            aria-valuenow="100"
                            aria-valuemin="0"
                            aria-valuemax="100"
                          ></div>
                        </div>
                      </div>
                    </td>
                  </tr>
                  <tr>
                    <td>
                      <div class="d-flex px-2 py-1">
                        <div>
                          <img
                            src="../assets/img/small-logos/logo-jira.svg"
                            class="avatar avatar-sm ms-3"
                          />
                        </div>
                        <div class="d-flex flex-column justify-content-center">
                          <h6 class="mb-0 text-sm">أضف صفحة التسعير الجديدة</h6>
                        </div>
                      </div>
                    </td>
                    <td>
                      <div class="avatar-group mt-2">
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Ryan Tompson"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-4.jpg"
                          />
                        </a>
                      </div>
                    </td>
                    <td class="align-middle text-center text-sm">
                      <span class="text-xs font-weight-bold">$500</span>
                    </td>
                    <td class="align-middle">
                      <div class="progress-wrapper w-75 mx-auto">
                        <div class="progress-info">
                          <div class="progress-percentage">
                            <span class="text-xs font-weight-bold">25%</span>
                          </div>
                        </div>
                        <div class="progress">
                          <div
                            class="progress-bar bg-gradient-info w-25"
                            role="progressbar"
                            aria-valuenow="25"
                            aria-valuemin="0"
                            aria-valuemax="25"
                          ></div>
                        </div>
                      </div>
                    </td>
                  </tr>
                  <tr>
                    <td>
                      <div class="d-flex px-2 py-1">
                        <div>
                          <img
                            src="../assets/img/small-logos/logo-invision.svg"
                            class="avatar avatar-sm ms-3"
                          />
                        </div>
                        <div class="d-flex flex-column justify-content-center">
                          <h6 class="mb-0 text-sm">
                            إعادة تصميم متجر جديد على الإنترنت
                          </h6>
                        </div>
                      </div>
                    </td>
                    <td>
                      <div class="avatar-group mt-2">
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Ryan Tompson"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-1.jpg"
                          />
                        </a>
                        <a
                          href="javascript:;"
                          class="avatar avatar-xs rounded-circle"
                          data-bs-toggle="tooltip"
                          data-bs-placement="bottom"
                          title
                          data-bs-original-title="Jessica Doe"
                        >
                          <img
                            alt="Image placeholder"
                            src="../assets/img/team-4.jpg"
                          />
                        </a>
                      </div>
                    </td>
                    <td class="align-middle text-center text-sm">
                      <span class="text-xs font-weight-bold">$2,000</span>
                    </td>
                    <td class="align-middle">
                      <div class="progress-wrapper w-75 mx-auto">
                        <div class="progress-info">
                          <div class="progress-percentage">
                            <span class="text-xs font-weight-bold">40%</span>
                          </div>
                        </div>
                        <div class="progress">
                          <div
                            class="progress-bar bg-gradient-info w-40"
                            role="progressbar"
                            aria-valuenow="40"
                            aria-valuemin="0"
                            aria-valuemax="40"
                          ></div>
                        </div>
                      </div>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
      <div class="col-lg-4 col-md-6">
        <timeline-list
          class="h-100"
          title="نظرة عامة على الطلبات"
          description="<i class='fa fa-arrow-up text-success' aria-hidden='true'></i>
        <span class='font-weight-bold'>24%</span> هذا الشهر"
        >
          <timeline-item
            color="success"
            icon="bell-55"
            title=" $2400, تغييرات في التصميم"
            date-time="22 DEC 7:20 PM"
          />
          <TimelineItem
            color="danger"
            icon="html5"
            title="طلب جديد #1832412"
            date-time="21 DEC 11 PM"
          />
          <TimelineItem
            color="info"
            icon="cart"
            title="مدفوعات الخادم لشهر أبريل"
            date-time="21 DEC 9:34 PM"
          />
          <TimelineItem
            color="warning"
            icon="credit-card"
            title="تمت إضافة بطاقة جديدة للطلب #4395133"
            date-time="20 DEC 2:20 AM"
          />
          <TimelineItem
            color="primary"
            icon="key-25"
            title="فتح الحزم من أجل التطوير"
            date-time="18 DEC 4:54 AM"
          />
          <TimelineItem
            color="dark"
            icon="ni ni-money-coins"
            title="طلب جديد #9583120"
            date-time="15 DEC"
          />
        </timeline-list>
      </div>
    </div>
  </div>
</template>

<script>
import MiniStatisticsCard from "@/examples/Cards/MiniStatisticsCard.vue";
import ReportsBarChart from "@/examples/Charts/ReportsBarChart";
import GradientLineChart from "@/examples/Charts/GradientLineChart.vue";
import TimelineList from "./components/TimelineList.vue";
import TimelineItem from "./components/TimelineItem.vue";

import setTooltip from "@/assets/js/tooltip.js";
import {
  faHandPointer,
  faUsers,
  faCreditCard,
  faScrewdriverWrench,
} from "@fortawesome/free-solid-svg-icons";

export default {
  name: "rtl-page",
  data() {
    return {
      iconBackground: "bg-gradient-success",
      faHandPointer,
      faUsers,
      faCreditCard,
      faScrewdriverWrench,
    };
  },
  components: {
    MiniStatisticsCard,
    ReportsBarChart,
    GradientLineChart,
    TimelineList,
    TimelineItem,
  },
  mounted() {
    setTooltip();
  },
  beforeMount() {
    this.$store.state.isRTL = true;
    document.querySelector("html").setAttribute("lang", "ar");
    document.querySelector("html").setAttribute("dir", "rtl");
    document.querySelector("#app").classList.add("rtl");
  },
  beforeUnmount() {
    this.$store.state.isRTL = false;
    document.querySelector("html").removeAttribute("lang");
    document.querySelector("html").removeAttribute("dir");
    document.querySelector("#app").classList.remove("rtl");
  },
};
</script>
