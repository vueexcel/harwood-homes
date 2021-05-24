<template>
  <q-page class="dashboard">
    <div class="header-spacer"></div>
    <div class="container-user">
      <div class="user-details">
        <div class="title">Hi, Edward Young</div>
        <div class="sub-title">Client</div>
        <img src="https://cdn.quasar.dev/img/avatar.png" alt="user" />
      </div>

      <q-input
        class="search-input"
        placeholder="Search in documents and projects"
        outlined
        bg-color="brown-1"
        borderless
        dense
      >
        <template v-slot:append>
          <q-icon name="search" />
        </template>
      </q-input>

      <div class="wrapper-grid">
        <div class="container-grid q-mt-sm">
          <div class="grid-item" v-for="n in 4" :key="n">
            <div class="wrapper-img">
              <img alt="house" src="~assets/house1.png" />
            </div>
            <div class="img-subtitle text-center text-uppercase q-mt-sm">
              design & build
            </div>
          </div>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: "PageIndex",
};
</script>

<style lang="scss">
.dashboard {
  background: url("./../assets/dashboard-bg.png"), rgba(0, 0, 0, 0.8);
  background-size: cover;
  position: absolute;
  top: 0;
  width: 100%;
  height: 100vh;
  .header-spacer {
    margin-top: 100px;
  }
  .container-user {
    background: #fff;
    height: 56vh;
    width: 100%;
    position: absolute;
    bottom: 80px;
    border-top: 8px solid rgba(161, 147, 134, 0.8);
    border-radius: 20px 20px 0 0;
    padding: 0 2.25rem;
    .user-details {
      position: absolute;
      right: 0;
      left: 0;
      margin-left: auto;
      margin-right: auto;
      text-align: center;
      top: 0;
      transform: translateY(-120px);
      .title {
        font-weight: bold;
        font-size: 15px;
        color: #ffffff;
      }
      .sub-title {
        font-size: 13px;
        text-transform: uppercase;
        color: #ffe6cf;
        margin-bottom: 0.6875rem;
      }
      img {
        border: 5px solid rgba(161, 147, 134, 1);
        border-radius: 50%;
        max-height: 7.75rem;
        max-width: 7.75rem;
        width: 100%;
      }
    }
    .search-input {
      margin-top: 4rem;
    }
    .wrapper-grid {
      overflow-y: scroll;
      height: calc(100% - 110px);
      .container-grid {
        display: grid;
        gap: 1.375rem;
        @media (min-width: 370px) {
          grid-template-columns: repeat(2, 1fr);
        }
        .grid-item {
          .wrapper-img {
            padding: 1.375rem 2.1875rem;
            background: #ffffff;
            box-shadow: 0px 3px 20px rgba(131, 131, 131, 0.15);
            border-radius: 8px;
            text-align: center;
            img {
              max-height: 4.125rem;
              max-width: 4.125rem;
            }
          }
          .img-subtitle {
            font-weight: bold;
            font-size: 11px;
          }
        }
      }
    }
  }
}
</style>
