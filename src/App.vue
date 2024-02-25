<template>
  <v-app>
    <v-navigation-drawer v-model="isDrawerOpen">
      <v-list>
        <v-list-subheader>Menu</v-list-subheader>
        <v-list-item prepend-icon="mdi-home">Home</v-list-item>
        <v-list-item prepend-icon="mdi-account">Users</v-list-item>
        <v-list-group value="Customers">
          <template #activator="{ props }">
            <v-list-item
              v-bind="props"
              prepend-icon="mdi-account-circle"
              title="Customers"
            >
            </v-list-item>
          </template>
          <v-list-item prepend-icon="mdi-currency-usd">Sales</v-list-item>
          <v-list-item prepend-icon="mdi-chart-line">Reports</v-list-item>
        </v-list-group>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar class="border-b">
      <v-app-bar-nav-icon
        @click="isDrawerOpen = !isDrawerOpen"
      ></v-app-bar-nav-icon>
      <v-app-bar-title>My app</v-app-bar-title>
      <template #append>
        <v-btn @click="toggleTheme">Toggle theme</v-btn>
        <v-btn icon class="mr-2" @click="alerta()">
          <v-badge dot color="info">
            <v-icon icon="mdi-bell-outline" size="x-large"></v-icon>
          </v-badge>
        </v-btn>
        <v-menu>
          <template #activator="{ props }">
            <v-avatar v-bind="props">
              <v-img
                src="https://images.pexels.com/photos/2381069/pexels-photo-2381069.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
              ></v-img>
            </v-avatar>
          </template>
          <v-card min-width="200px">
            <v-list lines="false" density="compact" nav>
              <v-list-item prepend-icon="mdi-account-outline">
                <v-list-item-title> My Account</v-list-item-title>
              </v-list-item>
              <v-list-item prepend-icon="mdi-heart-outline">
                <v-list-item-title>Favourite</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-card>
        </v-menu>
      </template>
    </v-app-bar>
    <v-main>
      <v-container>
        <h1 class="mb-6">Dashboard</h1>
        <v-card flat class="border mb-4">
          <div class="d-flex justify-space-between">
            <v-card-title>Last Users</v-card-title>
            <v-card-title>
              <v-btn @click="isDialogOpen = true" variant="tonal" size="small"
                >Add User</v-btn
              >
              <v-dialog v-model="isDialogOpen" width="600px">
                <v-card>
                  <v-card-title>Add User</v-card-title>
                  <v-card-text>
                    <v-row>
                      <v-col>
                        <v-text-field
                          label="Name"
                          variant="outlined"
                          :rules="nameRules"
                        ></v-text-field>
                      </v-col>
                      <v-col>
                        <v-text-field
                          label="Email"
                          variant="outlined"
                          :rules="emailRules"
                        ></v-text-field>
                      </v-col>
                    </v-row>
                    <v-select
                      label="Function"
                      variant="outlined"
                      :items="['Admin', 'Manager', 'Convidado']"
                    ></v-select>
                  </v-card-text>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn variant="text" @click="isDialogOpen = false"
                      >Cancelar</v-btn
                    >
                    <v-btn variant="tonal" color="success">Save</v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
            </v-card-title>
          </div>
          <v-table density="compact">
            <thead>
              <tr>
                <th>Name</th>
                <th>Email</th>
                <th>Function</th>
                <th>Action</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>Fulano</td>
                <td>fulano@gmail.com</td>
                <td>
                  <v-chip color="success" variant="outlined" size="small"
                    >Manager</v-chip
                  >
                </td>
                <td>
                  <v-btn variant="tonal" color="primary" size="small"
                    >Edit</v-btn
                  >
                </td>
              </tr>
              <tr>
                <td>Lucas Fortunato</td>
                <td>Lucas@gmail.com</td>
                <td>
                  <v-chip color="primary" variant="outlined" size="small"
                    >Admin</v-chip
                  >
                </td>
                <td>
                  <v-btn variant="tonal" color="primary" size="small"
                    >Edit</v-btn
                  >
                </td>
              </tr>
            </tbody>
          </v-table>
        </v-card>
        <v-row>
          <!-- Coluna card -->
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-card>
              <v-img
                src="https://images.pexels.com/photos/3662446/pexels-photo-3662446.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
                class="align-end text-white"
              >
                <v-card-title>Top 10 things to do in Nazaré</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">Sitio</v-card-subtitle>
              <v-card-text>
                <div>Mirante</div>
                <div>Lorem ipsum dolor sit amet.</div>
              </v-card-text>
              <v-card-actions>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="primary">
                  Ver mais
                </v-btn>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="alert"
                  >Comprar</v-btn
                >
              </v-card-actions>
            </v-card>
          </v-col>
          <!-- Coluna card -->
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-card>
              <v-img
                src="https://images.pexels.com/photos/3662446/pexels-photo-3662446.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
                class="align-end text-white"
              >
                <v-card-title>Top 10 things to do in Nazaré</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">Sitio</v-card-subtitle>
              <v-card-text>
                <div>Mirante</div>
                <div>Lorem ipsum dolor sit amet.</div>
              </v-card-text>
              <v-card-actions>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="primary">
                  Ver mais
                </v-btn>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="alert"
                  >Comprar</v-btn
                >
              </v-card-actions>
            </v-card>
          </v-col>
          <!-- Coluna card -->
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-card>
              <v-img
                src="https://images.pexels.com/photos/3662446/pexels-photo-3662446.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
                class="align-end text-white"
              >
                <v-card-title>Top 10 things to do in Nazaré</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">Sitio</v-card-subtitle>
              <v-card-text>
                <div>Mirante</div>
                <div>Lorem ipsum dolor sit amet.</div>
              </v-card-text>
              <v-card-actions>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="primary">
                  Ver mais
                </v-btn>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="alert"
                  >Comprar</v-btn
                >
              </v-card-actions>
            </v-card>
          </v-col>
          <!-- Coluna card -->
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-card>
              <v-img
                src="https://images.pexels.com/photos/3662446/pexels-photo-3662446.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
                class="align-end text-white"
              >
                <v-card-title>Top 10 things to do in Nazaré</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">Sitio</v-card-subtitle>
              <v-card-text>
                <div>Mirante</div>
                <div>Lorem ipsum dolor sit amet.</div>
              </v-card-text>
              <v-card-actions>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="primary">
                  Ver mais
                </v-btn>
                <v-btn prepend-icon="mdi-cart" variant="tonal" color="alert"
                  >Comprar</v-btn
                >
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>

      <HelloWorld />
    </v-main>
  </v-app>
</template>

<script>
import { ref } from "vue";
import { useTheme } from "vuetify";

export default {
  setup() {
    const alerta = () => {
      alert("No Notifications to show");
    };
    const theme = useTheme();
    const isDrawerOpen = ref(false);
    const isDialogOpen = ref(false);
    const nameRules = [
      (value) => {
        if (value) return true;

        return "Name is required.";
      },
      (value) => {
        if (value?.length <= 10) return true;

        return "Name must be less than 10 characters.";
      },
    ];
    const emailRules = [
      (value) => {
        if (value) return true;

        return "E-mail is requred.";
      },
      (value) => {
        if (/.+@.+\..+/.test(value)) return true;

        return "E-mail must be valid.";
      },
    ];
    function toggleTheme() {
      theme.global.name.value = theme.global.current.value.dark
        ? "light"
        : "dark";
    }
    return {
      alerta,
      isDrawerOpen,
      isDialogOpen,
      nameRules,
      emailRules,
      toggleTheme,
    };
  },
};
</script>
