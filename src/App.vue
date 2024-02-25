<template>
  <v-app theme="dark">
    <v-navigation-drawer v-model="isDrawerOpen">
      <v-list>
        <v-list-subheader>Menu</v-list-subheader>
        <v-list-item prepend-icon="mdi-home">Home</v-list-item>
        <v-list-item prepend-icon="mdi-account">Usuários</v-list-item>
        <v-list-group value="Clientes">
          <template #activator="{ props }">
            <v-list-item
              v-bind="props"
              prepend-icon="mdi-account-circle"
              title="Clientes"
            >
            </v-list-item>
          </template>
          <v-list-item prepend-icon="mdi-currency-usd">Vendas</v-list-item>
          <v-list-item prepend-icon="mdi-chart-line">Relatório</v-list-item>
        </v-list-group>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar class="border-b">
      <v-app-bar-nav-icon
        @click="isDrawerOpen = !isDrawerOpen"
      ></v-app-bar-nav-icon>
      <v-app-bar-title>Meu app</v-app-bar-title>
      <template #append>
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
                <v-list-item-title> Meu Perfil</v-list-item-title>
              </v-list-item>
              <v-list-item prepend-icon="mdi-heart-outline">
                <v-list-item-title> Favoritos</v-list-item-title>
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
            <v-card-title>Ultimos Usuários</v-card-title>
            <v-card-title>
              <v-dialog width="600px">
                <template #activator="{ props }">
                  <v-btn v-bind="props" variant="tonal" size="small">Adicionar Usuários</v-btn>
                </template>
                <v-card>
                  <v-card-text> test</v-card-text>
                </v-card>
              </v-dialog>
            </v-card-title>
          </div>
          <v-table density="compact">
            <thead>
              <tr>
                <th>Nome</th>
                <th>Email</th>
                <th>cargo</th>
                <th>Ações</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>Fulano</td>
                <td>fulano@gmail.com</td>
                <td>Admin</td>
                <td>
                  <v-btn variant="tonal" color="primary">Editar</v-btn>
                </td>
              </tr>
              <tr>
                <td>Lucas Fortunato</td>
                <td>Lucas@gmail.com</td>
                <td>Admin</td>
                <td>
                  <v-btn variant="tonal" color="primary">editar</v-btn>
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
export default {
  setup() {
    const alerta = () => {
      alert("No Notifications to show");
    };
    const isDrawerOpen = ref(false);
    return {
      alerta,
      isDrawerOpen,
    };
  },
};
</script>
