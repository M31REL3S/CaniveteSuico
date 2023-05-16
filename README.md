# CaniveteSuico

#include <iostream>
#include <array>
using namespace std;



//funcao para contar o nº de digitos
int contadorDigitos(long long int  n){
	int conta = 0;
	while(n > 0){
		n = n / 10;
		conta++;
	}	
	return conta;
}





//funcao para calcular expoente b^e
long long int expoente(int  b, int e){
	long long int resultado = 1;
	if(e != 0){
		for(int i = 1; i <= e; i++){
			resultado = resultado * b;
		}
	}
	return resultado;
}





//funcao converte numero binario para numero decimal
int converteBinarioParaDecimal(int numbinario){
	int decimal = 0, i = 0, digito;
	while(numbinario != 0){
		digito = numbinario % 10;
		numbinario = numbinario / 10;
		decimal = decimal + digito * expoente(2, i);
		i++;
	}
	return decimal;
}	


//funcao converte numero decimal para numero binario
int converteDecimalParaBinario(int numdecimal)
{
	int decimal = 0;
	 int i = 0;
	int resto;
	while(numdecimal > 0)
	{
		resto = numdecimal % 2;
		numdecimal = numdecimal / 2;
		decimal = decimal += resto * expoente(10,i);
		i++;
	}return decimal;
}




//funcao converter velocidade Km/h para m/s
float converterVelocidade(float x)
{
	return x / 3.6;	
}




//funcao subtrair numeros
int subtrairnumeros (int numsub1, int numsub2)
{
	int numeros;
	numeros = numsub1 - numsub2;
	return numeros;
}



//funcao somar numeros
int somarnumeros (int numsom1, int numsom2)
{
	int numeros;
	numeros = numsom1 + numsom2;
	return numeros;
}



//funcao dividir numeros
int dividirnumeros (int numdiv1, int divisor)
{	
	int numeros;
	numeros = numdiv1 / divisor;
	return numeros;
}



//funcao multiplicar numeros
int multiplicarnumeros (int num1mult, int num2mult)
{
	int numeros;
	numeros = num1mult * num2mult;
	return numeros;
}




//MENU
char menu(){
	char op;
	cout<<"---MENU OPCOES\n";
	cout<<"| X- SAIR DO PROGRAMA"<<endl;
	cout<<"| 1- CONVERTE PARA DECIMAL"<<endl;
	cout<<"| 2- CONVERTE PARA BINARIO"<<endl;
	cout<<"| 3- CONVERTE KM/H PARA M/S"<<endl;
	cout<<"| 4- TABUADA"<<endl;
	cout<<"---"<<endl;
	cout<<"Escolha a opcao:";
	cin>>op;
	return op;	
}



//SUBMENU
char submenu(){
	char opp;
	cout<<"---SUBMENU TABUADA"<<endl;
	cout<<"| X- SAIR DO SUBMENU"<<endl;
	cout<<"| 1- SUBTRACAO"<<endl;
	cout<<"| 2- ADICAO"<<endl;
	cout<<"| 3- DIVISAO"<<endl;
	cout<<"| 4- MULTIPLICACAO"<<endl;
	cout<<"---\n";
	cout<<"Escolha uma opcao: ";
	cin>>opp;
	return opp;
}





//PROGRAMA 
int main()
{
	char opcao, oppcao;
	int bin, binn;
	float velocidade;
	do{
		opcao = menu();
		switch(opcao)
		{
			case  'X':
				cout<<"O programa vai terminar !"<<endl;
				break;
				
			case  'x':
				cout<<"O programa vai terminar !"<<endl;
				break;
				
				
				case '1' :
				cout<<"Opcao de converter binario para decimal"<<endl;
				cout<<"Insira um numero: ";
				cin>>bin;
				cout << "O numero binario em decimal: "<<converteBinarioParaDecimal(bin)<<endl;
				break;
				
			case '2': 
				cout<<"Opcao de converter decimal para binario"<<endl;
				cout<<"Insira um numero: ";
				cin>>binn;
				cout << "O numero decimal em binario: "<<converteDecimalParaBinario(binn)<<endl;	
				break;
				
			case '3':
				cout<<"Opcao de converter Km/h para m/s"<<endl;
				cout<<"Insira a velocidade em Km/h: ";
				cin>>velocidade;
				cout << "A velocidade em m/s: "<<converterVelocidade(velocidade)<<endl;	
				break;
			case '4':
				int num1sub, num2sub, num1som, num2som, num1div, divisor, num1mult, num2mult;
				oppcao = submenu();
				switch(oppcao)
				{
					case 'X': 
						cout<<"O submenu vai fechar !"<<endl;
						break;
					case  'x':
						cout<<"O submenu vai fechar !"<<endl;
						break;
					case '1' :
						cout<<"Opcao de subtrair numeros !\n";
						cout<<"Insira um numero: ";
						cin>> num1sub;
						cout<<"Insira outro numero: ";
						cin>> num2sub;
						cout<<"A subtracao dos dois numeros e: "<<subtrairnumeros(num1sub, num2sub)<<endl;
						break;
					case '2':
						cout<<"Opcao de somar numeros !\n";
						cout<<"Insira um numero: ";
						cin>> num1som;
						cout<<"Insira outro numero: ";
						cin>> num2som;
						cout<<"A soma dos dois numeros e: "<<somarnumeros(num1som, num2som)<<endl;
						break;
					case '3': 
						cout<<"Opcao de dividir numeros !\n";
						cout<<"Insira um numero: ";
						cin>> num1div;
						do{
							cout<<"Insira outro numero: ";
							cin>> divisor;
						}while(divisor == 0);
						cout<<"A divisao dos dois numeros e: "<<dividirnumeros(num1div, divisor)<<endl;
						break;
					case '4':
						cout<<"Opcao de multiplicar numeros !\n";
						cout<<"Insira um numero: ";
						cin>> num1mult;
						cout<<"Insira outro numero: ";
						cin>> num2mult;
						cout<<"A multiplicacao dos dois numeros e: "<<multiplicarnumeros(num1mult, num2mult)<<endl;
					default :
						cout<<"Opcao invalida :";
				}	
				break;	
			default :
				cout<<"Opcao invalida :";
		}
	}while(opcao != 'X' && opcao != 'x');
	return 0;
}
	
