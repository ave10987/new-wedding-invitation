<template>
  <div class="page-wrapper invitation">
    <Header />
    <div class="content-wrapper">
      <Title :text="'Invitation'" />
      <div class="message flex-item korean">
        "이 사람이라고 생각했습니다. <br /> 그래서 결혼합니다"
      </div>
      <div class="parents flex-item">
        <div class="table-wrapper korean">
          <table>
            <tr>
              <td class="name right">윤창혁</td>
              <td rowspan="2" class="small left">의</td>
              <td rowspan="2" class="small right">장남</td>
              <td rowspan="2" class="green-text name left bold">윤정현</td>
            </tr>
            <tr>
              <td class="name right">최승자</td>
            </tr>
          </table>
          <table class="name-table-margin">
            <tr>
              <td class="name right">임명화</td>
              <td rowspan="2" class="small left">의</td>
              <td rowspan="2" class="small right">장녀</td>
              <td rowspan="2" class="green-text name left bold">최정민</td>
            </tr>
          </table>
        </div>
      </div>
      <div class="flex-item description">
        <div class="korean time">10월 28일(일) 2PM</div>
        <div class="korean location">양재역 브라이드 밸리</div>
      </div>
    </div>
  </div>
</template>
<script>
import Header from './Header';
import Title from './Title';

export default {
  name: 'Invitation',
  components: {
    Header,
    Title,
  },
};
</script>
<style>
  .invitation .content-wrapper .message {
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    line-height: 32px;
    font-weight: 800;
    text-align: center;
  }
  .invitation .content-wrapper .parents {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .invitation .content-wrapper .parents .table-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: #c7ceb4;
    margin: 0 10px;
    border-radius: 10px;
    font-size: 20px;
    font-weight: 400;
    text-align: center;
    width: 100%;
  }
  .invitation .content-wrapper .parents .table-wrapper table {
    width: 100%;
    margin: 20px 0;
  }
  .invitation .content-wrapper .parents .table-wrapper table td.right {
    text-align: right;
  }
  .invitation .content-wrapper .parents .table-wrapper table td.left {
    text-align: left;
  }
  .invitation .content-wrapper .parents .table-wrapper table td {
    font-size: 22px;
  }
  .invitation .content-wrapper .parents .table-wrapper table td.small {
    font-size: 16px;
  }
  .invitation .content-wrapper .parents .table-wrapper table td.name {
    padding: 0 10px;
  }
  .invitation .content-wrapper .parents .table-wrapper table td.bold {
    font-size: 24px;
    font-weight: 800;
  }
  .invitation .content-wrapper .description {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: top;
  }
  .invitation .content-wrapper .description .time {
    font-size: 26px;
    font-weight: 800;
    margin: 10px 0;
  }
  .invitation .content-wrapper .description .location {
    font-size: 20px;
    font-weight: 400;
    margin: 10px 0;
  }
</style>
