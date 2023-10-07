#include <stdio.h>
#include <stdlib.h>
#include <string.h>

const char *descuento[] = {
    "8949899430",
    "7653512593",
    "9383867373",
    "88392904209"
};

const char *rifa[] = {
    "894985943020763",
    "165331255320221",
    "248386737320130",
    "183923092220561"
};

int tdescuento(const char *codigopro) {
  for (int i = 0; i < sizeof(descuento) / sizeof(descuento[0]); i++) {
    if (strcmp(codigopro, descuento[i]) == 0) {
      return 1;
    }
  }
  return 0;
}

int participar(const char *codigopro, const char *almacen) {
  char numcombinado[15];
  strcpy(numcombinado, codigopro);
  strcat(numcombinado, almacen);
  for (int i = 0; i < sizeof(rifa) / sizeof(rifa[0]); i++) {
    if (strcmp(numcombinado, rifa[i]) == 0) {
      return 1;
    }
  }
  return 0;
}

int main() {
  char codigopro[11];
  char almacen[6];
  printf("Digite el codigo de barra: ");
  scanf("%s", codigopro);
  printf("Digie el codigo del almacen: ");
  scanf("%s", almacen);

  if (strlen(codigopro) != 10) {
    printf("El codigo de barra digitado no cumple con los 10 numeros correspondientes, itentelo nuevamente");
    return 1;
  }
  if (strlen(almacen) != 5 || almacen[0] != '2') {
    printf("El codigo del almacen debe tener 5 digitos y empezar por el prefijo 20, itentelo nuevamente");
    return 1;
  }

  int descuento = tdescuento(codigopro);
  int ganador = participar(codigopro, almacen);

  if (descuento) {
    printf("El producto tiene un descuento del 20%./n");
  } else {
    printf("El producto no tiene descuento/n");
  }
  if (ganador) {
    printf("El producto puede participar en la rifa del vehiculo");
  } else {
    printf("El producto no puede participar en la rifa del vehiculo");
  }
  return 0;
}
