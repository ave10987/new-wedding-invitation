<template>
  <div class="page-wrapper location">
    <Header />
    <div class="content-wrapper">
      <Title :text="'Location'" />
      <div class="flex-item address">
        <div class="korean address-detail">양재역 브라이드 밸리</div>
        <div class="korean address-detail-small">서울 특별시 강남구 강남대로 262, 지하 1층<br />(도곡동 캠코 양재타워)</div>
      </div>
      <div id="map" class="map flex-item"></div>
      <div class="buttons">
        <a class="tmap" href="tmap://?rGoName=브라이드밸리&rGoX=127.033433&rGoY=37.486922">
          <img src="../../static/img/tmap.jpg" alt="">
        </a>
        <a href="#" @click.prevent="goKakaoNavi()" class="kakao">
          <img src="../../static/img/kakao.jpg" alt="">
        </a>
      </div>
      <div class="transportation flex-item">
        <div class="subway">
          <img src="../../static/img/subway.png" alt="" height="30">
          <span class="desc">양재역 3번출구에서 도보 2분거리</span>
        </div>
        <div class="bus">
          <img src="../../static/img/bus.png" alt="" height="30">
          <span class="desc small">
            간선 140, 400, 402, 407, 421, 440, 441, 462, 470
            <br />
            직행 1005-1, 1550, 1570, 3002, 3007, 9700
          </span>
        </div>
        <div class="car">
          <img src="../../static/img/car.png" alt="" height="30">
          <span class="desc">도곡동 캠코 양재타워 주차장<br />
            인포데스크에서 차량번호 등록 (무료주차 2시간)</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Header from './Header';
import Title from './Title';

export default {
  name: 'Location',
  components: {
    Header,
    Title,
  },
  methods: {
    goKakaoNavi() {
      window.Kakao.Navi.start({
        name: '브라이드밸리',
        x: 127.033433,
        y: 37.486922,
        coordType: 'wgs84',
      });
    },
  },
  mounted() {
    const center = new window.naver.maps.LatLng(37.486922, 127.033433);
    const map = new window.naver.maps.Map('map', {
      center,
      zoom: 10,
      scaleControl: false,
      logoControl: false,
      mapDataControl: false,
      mapTypeControl: false,
      zoomControl: true,
      zoomControlOptions: {
        style: window.naver.maps.ZoomControlStyle.SMALL,
        position: window.naver.maps.Position.RIGHT_TOP,
      },
    });

    const mapElement = map.getElement();
    window.naver.maps.Event.addDOMListener(mapElement, 'touchstart', (e) => {
      e.stopPropagation();
    });

    const markerOptions = {
      position: center,
      map,
      icon: {
        url: '../../static/img/heart_icon.png',
        size: new window.naver.maps.Size(22, 35),
        origin: new window.naver.maps.Point(0, 0),
        anchor: new window.naver.maps.Point(11, 35),
      },
    };
    /*eslint-disable*/
    new window.naver.maps.Marker(markerOptions);
  },
};
</script>
<style>
  .location .content-wrapper .address {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
  }
  .location .content-wrapper .address .address-detail {
    font-size: 20px;
    font-weight: 800;
    text-align: center;
    margin: 10px 0;
  }
  .location .content-wrapper .address .address-detail-small {
    font-size: 14px;
    margin: 5px 0 15px 0;
  }
  .location .content-wrapper .map {
    margin: 0 10px;
    height: 180px;
  }
  .location .content-wrapper .buttons {
    display: flex;
    flex-direction: row;
  }
  .location .content-wrapper .buttons a {
    flex: 1;
    border-radius: 10px;
    margin: 10px;
    padding: 10px;
    height: 25px;
    text-align: center;
    border: 1px solid rgba(143, 143, 143, .5);
  }
  .location .content-wrapper .buttons img {
    height: 25px;
  }
  .location .content-wrapper .buttons a.tmap {
    background-color: #ececec;
  }
  .location .content-wrapper .buttons a.kakao {
    background-color: #f9e200;
  }
  .location .content-wrapper .transportation {
    margin: 0 10px;
    font-size: 14px;
  }
  .location .content-wrapper .transportation div {
    display: flex;
    align-items: center;
    margin: 10px 0;
  }
  .location .content-wrapper .transportation span {
    display: inline-block;
    margin: 0 0 0 10px;
  }
  .location .content-wrapper .transportation span.small {
    font-size: 13px;
  }
</style>
