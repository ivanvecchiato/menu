<template>
  <div class="report">
    <div class="container">
      <div class="header">PRANZO</div>
      <div class="form-group">
        <div v-for="item in items.pranzo.primi" :key="item.id" class="form-row">
          <input type="text" size="12" v-model="item.name"/>
          <input type="text" size="1" v-model="item.quantity.regular"/>
          <input type="text" size="1" v-model="item.quantity.small"/>
        </div>
      </div>
      <div class="form-group">
        <div v-for="item in items.pranzo.secondi" :key="item.id" class="form-row">
          <input type="text" size="12" v-model="item.name"/>
          <input type="text" size="1" v-model="item.quantity.regular"/>
          <input type="text" size="1" v-model="item.quantity.small"/>
        </div>
      </div>
      <div class="header">CENA</div>
      <div class="form-group">
        <div v-for="item in items.cena.primi" :key="item.id" class="form-row">
          <input type="text" size="12" v-model="item.name"/>
          <input type="text" size="1" v-model="item.quantity.regular"/>
          <input type="text" size="1" v-model="item.quantity.small"/>
        </div>
      </div>
      <div class="form-group">
        <div v-for="item in items.cena.secondi" :key="item.id" class="form-row">
          <input type="text" size="12" v-model="item.name"/>
          <input type="text" size="1" v-model="item.quantity.regular"/>
          <input type="text" size="1" v-model="item.quantity.small"/>
        </div>
      </div>
    </div>
    <div class="buttons">
      <button>prev</button>
      <button>next</button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'HomeView',
  components: {
  },
  data() {
    return {
      items: {
        pranzo: {
          primi: [],
          secondi: []
        },
        cena: {
          primi: [],
          secondi: []
        }
      },
      num_of_items: 8
    }
  },
  methods: {
    composeItems: function() {
      for(var i=0; i<this.num_of_items; i++) {
        var item = {
          id: 'pp' + (i+1),
          name: 'item ' + (i+1),
          quantity: {
            regular: 0,
            small: 0
          }
        }

        this.items.pranzo.primi.push(item);
      }
      for(i=0; i<this.num_of_items; i++) {
        item = {
          id: 'ps' + (i+1),
          name: 'item ' + (i+1),
          quantity: {
            regular: 0,
            small: 0
          }
        }

        this.items.pranzo.secondi.push(item);
      }
      for(i=0; i<this.num_of_items; i++) {
        item = {
          id: 'cp' + (i+1),
          name: 'item ' + (i+1),
          quantity: {
            regular: 0,
            small: 0
          }
        }

        this.items.cena.primi.push(item);
      }
      for(i=0; i<this.num_of_items; i++) {
        item = {
          id: 'cs' + (i+1),
          name: 'item ' + (i+1),
          quantity: {
            regular: 0,
            small: 0
          }
        }

        this.items.cena.secondi.push(item);
      }
    }
  },
  mounted() {
    this.composeItems();
    console.log(this.items)
  }


}
</script>

<style scoped>
.report {
  text-align: center;
}
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 8px;
}
.form-group {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 8px;
  width: 100%;
  & > span,
  .form-field {
      white-space: nowrap;
      display: block;
      &:not(:first-child):not(:last-child) {
          border-radius: 0;
      }
      &:first-child {
          border-radius: 6px 0 0 6px;
      }
      &:last-child {
          border-radius: 0 6px 6px 0;
      }
      &:not(:first-child) {
          margin-left: -1px;
      }
  }
.form-row {
  display: flex;
  gap: 4px;
}
  .form-field {
      position: relative;
      z-index: 1;
      flex: 1 1 auto;
      width: 1%;
      margin-top: 0;
      margin-bottom: 0;
  }
  & > span {
      text-align: center;
      padding: 8px 12px;
      font-size: 14px;
      line-height: 25px;
      color: var(--group-color);
      background: var(--group-background);
      border: 1px solid var(--group-border);
      transition: background .3s ease, border .3s ease, color .3s ease;
  }
  &:focus-within {
      & > span {
          color: var(--group-color-focus);
          background: var(--group-background-focus);
          border-color: var(--group-border-focus);
      }
  }
}
.header {
  grid-column: span 2;
  font-size: 1.2em;
  font-weight: bold;
  margin: 10px;
}
.buttons {
  margin: 10px;
}
</style>