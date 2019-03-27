//Realizar la tabla de la verdad con 6 variables, el cual mostrara
//el nuemero de fila solicitado por el usuario

#include <stdio.h>
#include <math.h>
#include <stdlib.h>

main(){
	
	int result = 0, i = 0, numero = 0;
	int contador = 1, divisor = 2;
	int fila = 0, columna = 0;
	int potencia = 0;
	int tabla[130][10];
	
	printf("Ingrese el numero de variables que desea: ");
	scanf("%d", &numero);
	printf("\n");
	
	potencia = pow(2,numero);
	
	for (int columna=0; columna<numero; columna++){
		i =0;
		contador=1;
		result = potencia / divisor;
		do {
			for (int fila=i; fila<i+result; fila++){
				if(contador%2==0){
					tabla[fila][columna] = 1;
				} else {
					tabla[fila][columna] = 0;
				}
			}
			contador=contador+1;
			i = i+result;
		} while (i<potencia);
		divisor = divisor * 2;
	}
	
	for(int fila=0; fila<potencia; fila++){
		for(int columna=0; columna<numero; columna++){
			printf("%d ", tabla[fila][columna]);
		}
		printf("\n");
	}
	int dato;
	
	printf("\n");
	printf("Digite el numero de la fila que desea resaltar: ");
	scanf("%d", &dato);
	printf("\n");
	
	while (dato>potencia)
	{
		printf("El numero digitado es muy grande\n");
		printf("Por favor digitar un numero menor o igual a %d\n", potencia);
		scanf("%d", &dato);
		printf("\n");
	}
	dato=dato-1;

	for(int fila=0; fila<potencia; fila++){
		for(int columna=0; columna<numero; columna++){
			if (fila==dato){
				printf(" * %d",tabla[fila][columna]);
			} else {
				printf("%d ",tabla[fila][columna]);
			}
		}
		printf("\n");
	}
	system("pause>null");
	return 0;
}
