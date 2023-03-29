      <template> 
        <div class="table-wrapper">
          <table class="table">
            <thead class="thead-dark">
              <tr>
                <th scope="col" id="id">ID</th>
                <th scope="col" id="name">NOMBRE</th>
                <th scope="col" id="fecha">FECHA DE NACIMIENTO</th>
                <th scope="col" id="">LINK</th>
                <th scope="col">BUTTON</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="user in users" :key="user">
                <td>1</td>
                <td><input type="text" v-model="user.nombre1" /></td>
                <td><input type="date" v-model="user.fechaNacimiento1" /></td>
                <td><input type="text" v-model="user.link1" /></td>

                <button
                  class="boton-lateral"
                  v-for="btn in buttons"
                  :key="btn.id"
                  :disabled="btn.disabled"
                  @click="buttonClicked(btn)"
                  id="text1"
                >
                  SUBMIT
                  {{ btn.text1 }}
                </button>
              </tr>
              <tr v-for="user in users" :key="user">
                <td>2</td>
                <td><input type="text" v-model="user.nombre2" /></td>
                <td><input type="date" v-model="user.fechaNacimiento2" /></td>
                <td><input type="text" v-model="user.link2" /></td>
                <button
                  class="boton-lateral"
                  v-for="btn in buttons"
                  :key="btn.id"
                  :disabled="btn.disabled"
                  @click="buttonClicked(btn)"
                >
                  SUBMIT
                  {{ btn.text2 }}
                </button>
              </tr>

              <tr v-for="user in users" :key="user">
                <td>3</td>
                <td><input type="text" v-model="user.nombre3" /></td>
                <td><input type="date" v-model="user.fechaNacimiento3" /></td>
                <td><input type="text" v-model="user.link3" /></td>
                <button
                  class="boton-lateral"
                  v-for="btn in buttons"
                  :key="btn.id"
                  :disabled="btn.disabled"
                  @click="buttonClicked(btn)"
                >
                  SUBMIT
                  {{ btn.text3 }}
                </button>
              </tr>
              <tr v-for="user in users" :key="user">
                <td>4</td>
                <td><input type="text" v-model="user.nombre4" /></td>
                <td><input type="date" v-model="user.fechaNacimiento4" /></td>
                <td><input type="text" v-model="user.link4" /></td>
                <button
                  class="boton-lateral"
                  v-for="btn in buttons"
                  :key="btn.id"
                  :disabled="btn.disabled"
                  @click="buttonClicked(btn)"
                >
                  SUBMIT
                  {{ btn.text4 }}
                </button>
              </tr>
              <tr v-for="user in users" :key="user">
                <td>5</td>
                <td><input type="text" v-model="user.nombre5" /></td>
                <td><input type="date" v-model="user.fechaNacimiento5" /></td>
                <td><input type="text" v-model="user.link5" /></td>

                <button
                  class="boton-lateral"
                  v-for="btn in buttons"
                  :key="btn.id"
                  :disabled="btn.disabled"
                  @click="buttonClicked(btn)"
                >
                  SUBMIT
                  {{ btn.text5 }}
                </button>
              </tr>
              <tr>
                <td>y</td>
                <td>
                  <button @click="updateUser(users, 'users', users.nombre)">
                    Guardar
                  </button>
                </td>
                <td>
                  <button @click="updateUser(users, 'users', users.fechaNacimiento)">
                    Guardar
                  </button>
                </td>
                <td>
                  <button @click="updateUser(users, 'users', users.link)">
                    Guardar
                  </button>
                </td>
                <span></span>
              </tr>
            </tbody>
          </table>
        </div>
      </template>

      <script>
      export default {
        name: "MyExample",
        data: function () {
          return {
            buttons: [{}],

            users: [{}],
            updatedUser: {},
          };
        },
        methods: {
          buttonClicked: function (button) {
            button.disabled = false;
            alert(button.text + " clicked!");
          },
          enableAllBtns: function () {
            this.buttons.forEach(function (button) {
              button.disabled = false;
            });
          },
          updateUser(user, column, value) {
            this.updatedUser = { ...user, [column]: value };
          },
          saveUser() {
            // Aquí iría la lógica para guardar los cambios en la base de datos
            console.log("Usuario actualizado:", this.updatedUser);
          },
        },
      };
      </script>

      <style>
      .table-wrapper {
        width: 800px;
        height: max-content;
        overflow-block: scroll;
        padding: 40px;
      }
      .boton-lateral {
        text-decoration: none;
        font-weight: 200;
        font-size: 10px;
        color: hsl(0, 85%, 8%);
        padding-top: 5px;
        padding-bottom: 5px;
        padding-left: 15px;
        padding-right: 15px;
        background-color: #73484919;
        border-color: #51363795;
        border-width: 3px;
        border-style: solid;
        font-weight: bold;
      }

      table {
        border-collapse: separate;
        width: max-content;
        height: max-content;
        color: rgb(11, 12, 18);
        font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
        font-size: 12px;
        text-align: left;
        margin-bottom: 100px;
        margin: 0 auto;
      }
      th,
      td {
        padding: inherit;
        border: 1px solid rgba(83, 57, 57, 0.53);
      }
      th {
        text-align: center;
        vertical-align: middle;
      }
      th {
        background-color: #085b0c;
        color: #ffffff;
      }
      tr:nth-child(even) {
        background-color: #4caf50;
      }
      </style>


