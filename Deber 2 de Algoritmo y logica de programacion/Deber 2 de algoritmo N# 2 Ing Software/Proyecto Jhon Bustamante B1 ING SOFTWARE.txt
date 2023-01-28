// funciones o SubAlgoritmo  del proyecto
// SubAlgoritmo menus del proyecto
Funcion opcion = presentarMenu(titulo,menu,lim)
	Definir opcion Como Caracter
	Definir pos Como Entero
	Borrar Pantalla
	Escribir titulo
	Para pos<-0 Hasta lim-1 Hacer
		Escribir menu[pos]
	FinPara
	Escribir '       Elija opción[1..',lim,']' Sin Saltar
	Leer opcion
FinFuncion

// SubAlgoritmo mayorDosNumeros()
// esta funcion pide dos numeros y presenta el mayor de los dos
Funcion mayorDosNumeros()
	Definir num1,num2 Como Entero
	Escribir 'Ingrese numero1'
	Leer num1
	Escribir 'Ingrese numero2'
	Leer num2
	Si num1>num2 Entonces
		Escribir num1,' Es mayor que ',num2
	SiNo
		Si num1<num2 Entonces
			Escribir num1,' Es menor que ',num2
		SiNo
			Escribir num1,' Es igual a ',num2
		FinSi
	FinSi
FinFuncion

// Esta funcion pide 2 numeros y los divide restandolos
Funcion dividirDosNumerosResta()
	Escribir 'Ingrese numero1'
	Leer dividendo
	Escribir 'Ingrese numero2'
	Leer divisor
	Mientras dividendo>=divisor Hacer
		dividendo <- dividendo-divisor
		cociente <- cociente+1
	FinMientras
	Escribir 'El resultado de la division mediante resta es: ',cociente
FinFuncion

// Multiplicar 2 numeros mediante suma
Funcion MultiDosNumerosSuma()
	Escribir 'Ingrese numero1'
	Leer multiplicando
	Escribir 'Ingrese numero2'
	Leer multiplicador
	Para i<-1 Hasta multiplicando Hacer
		acu <- acu+multiplicador
	FinPara
	Escribir 'El resultado de la multiplicacion mediante suma es: ',acu
FinFuncion

// 4)Suma Pares y Productos multiplos de 5 de una secuencia de numeros"
Funcion Sumaparesymultiplosde5()
	Definir sumapares,multi,num Como Entero
	multi <- 1
	Para i<-1 Hasta 5 Hacer
		Escribir 'Ingrese 5 numeros'
		Leer num
		Si num MOD 2=0 Entonces
			sumapares <- sumapares+num
		FinSi
		Si num MOD 5=0 Entonces
			multi <- multi*num
		FinSi
		c <- c+1
	FinPara
	Escribir 'La suma de los pares es: ',sumapares
	Escribir 'El productos multiplos de 5 es: ',multi
FinFuncion

// 5)Presentar cantidad de digitos de todos los numeros de una secuencia de numeros hasta 0
// 2,123,10,2345,0 respuesta = 10    r=trunc(2/10)=0 r = 2 mod 10 =2
Funcion secuencianum()
	Escribir 'Ingrese un numero'
	Leer num
	Mientras num<>0 Hacer
		Mientras num>0 Hacer
			num <- trunc(num/10)
			c <- c+1
		FinMientras
		Escribir 'Ingrese un numero'
		Leer num
	FinMientras
	Escribir 'La cantidad de digitos es : ',c
FinFuncion

// El almacen SomosMas tiene una promoción: a todos los trajes que tienen un
// precio superior a 100, se les aplicará un descuento del 10 MOD   y a los demas
// el 5 MOD . presentar el valor de cada traje con su respectivo valor, descuento y pago
// considerando el iva del 12 MOD . Asuma que se ingresan n trajes.
// n=2
// PrecioTraje=120   des=precioTraje*0.10=12  iva=(120-12)*0.12 pago=precioTraje-des+iva
// PrecioTraje=50   des=precioTraje*0.05=2.5  iva=(50-2.5)*0.12
Funcion promocionalmacen()
	Escribir 'Ingrese la cantidad de trajes comprados'
	Leer cantidadtrajes
	Para i<-1 Hasta cantidadtrajes Hacer
		Escribir 'Ingrese precio del traje: '
		Leer preciotraje
		Si preciotraje>=100 Entonces
			des <- preciotraje*0.90
			iva <- (des*0.12)+des
			Escribir 'El precio del traje es de: ',preciotraje
			Escribir 'El precio + descuento es de: ',des
			Escribir 'El precio + decuento + iva 12% es: ',iva
		SiNo
			des <- preciotraje*0.95
			iva <- (des*0.12)+des
			Escribir 'El precio del traje es de: ',preciotraje
			Escribir 'El precio + descuento es de: ',des
			Escribir 'El precio + decuento + iva 12% es: ',iva
		FinSi
	FinPara
FinFuncion

// 7)Dado tres numeros indicar si el segundo es el mayor
// 2,5,8= 5 no es mayor			2,9,3=  9 si es mayor
Funcion mayornumeros()
	Escribir 'Ingrese 3 numeros'
	Leer n1,n2,n3
	Si n2>n1 Y n2>n3 Entonces
		Escribir 'El segundo numero si es el mayor entre los 3 de la secuencia'
	SiNo
		Escribir 'El segundo numero no es el mayor entre los 3 de la secuencia'
	FinSi
FinFuncion

// 8)Dado una secuencia de numeros presentar su promedio
// la secuencia termina cuando se ingrese un numero negativo
// 2,4,6,8,-10
Funcion promediosecuencia()
	Definir num,ci Como Entero
	Definir prom Como Real
	acu <- 0
	ci <- 0
	// prom=(num+acu)/numeros
	Repetir
		Escribir 'Escribe un numero'
		Leer num
		Si num>=0 Entonces
			acu <- acu+num
			ci <- ci+1
			prom <- acu/ci
		FinSi
	Hasta Que num<=0
	Escribir 'La suma de los numeros de la secuencia es: ',acu
	Escribir 'La cantidad de numeros ingresados son: ',ci
	Escribir 'El promedio es de: ',prom
FinFuncion

// dos numeros son amigos cuando la suma de los divisores del primer numero
// son iguales a la suma de los divisores del segundo numero.
// n1=6(1,2,3)=6 n2=25(1,5)=6
Funcion numerosamigos()
	Definir num1,num2 Como Entero
	Escribir 'Ingrese el primer numero'
	Leer num1
	Escribir 'Ingrese el segundo numero'
	Leer num2
	suma1 <- 0
	suma2 <- 0
	Para i<-1 Hasta num1-1 Hacer
		Si num1 MOD i=0 Entonces
			suma1 <- suma1+i
			// Mostrar i
		FinSi
	FinPara
	Para i<-1 Hasta num2-1 Hacer
		Si num2 MOD i=0 Entonces
			suma2 <- suma2+i
			// Mostrar i
		FinSi
	FinPara
	Escribir 'La suma de los divisores del primer numero es: ',suma1
	Escribir 'La suma de los divisores del segundo numero es: ',suma2
	Si suma1=suma2 Entonces
		Escribir '[(----los numeros ingresados son gemelos----)]'
	SiNo
		Escribir '[(----los numeros ingresados no son gemelos----)]'
	FinSi
FinFuncion

// dos numeros son primos gemelos si ambos son primos
Funcion primosgemelos()
	Definir num1,num2 Como Entero
	Escribir 'Ingrese el primer numero'
	Leer num1
	Escribir 'Ingrese el segundo numero'
	Leer num2
	suma1 <- 0
	suma2 <- 0
	Para i<-1 Hasta num1 Hacer
		Si num1 MOD i=0 Entonces
			suma1 <- suma1+i
			// Mostrar i
		FinSi
	FinPara
	Para i<-1 Hasta num2 Hacer
		suma2 <- suma2+i
		// Mostrar i
	FinPara
	Si num1=suma1-1  Entonces
		Escribir '[(----Los numeros son primos gemelos----)]'
	SiNo
		si suma2-1=num2 Entonces
			Escribir '[(----Los numeros son primos gemelos----)]'
		SiNo
			Escribir '[(----Los numeros no son primos gemelos----)]'
		FinSi
	FinSi
FinFuncion

// ejercicios Cadenass
// Ingresar un nombre y presentar el nombre carácter x caracter
Funcion nombreCaracter()
	Escribir 'Escriba el nombre: '
	Leer nombre
	r <- longitud(nombre)
	Para i<-0 Hasta r Hacer
		ci <- SubCadena(nombre,i,i)
		Escribir ci
		c <- c+1
	FinPara
FinFuncion

// frase="hola que tal"    hql
// 2)Presentar el primero, el medio y el ultimo caracter de una fras
Funcion primermedioyultimo()
	Definir frase Como Caracter
	Escribir 'Ingresar frase'
	Leer frase // hola que tal
	lon <- longitud(frase)
	c <- lon/2
	Para i<-0 Hasta lon Con Paso c Hacer
		r <- SubCadena(frase,i,i)
		
		Escribir '[ ',r,' ]' Sin Saltar
		Si i=0 Entonces
			i <- i-1
		FinSi
	FinPara
FinFuncion

//nom1="daniel" nombre2="daniel" si nombre1 = nombre2
Funcion nombreigual()
	Definir nombre1, nombre2 Como Caracter
	
	Escribir "Ingrese nombre 1"
	Leer nombre1
	Escribir "Ingrese nombre 2"
	Leer nombre2
	
	si nombre1=nombre2 Entonces
		Escribir "Los nombres son iguales..."
	SiNo
		Escribir "Los nombres son distintos..."
	FinSi
FinFuncion

//f1="Hola" f2="mal"  si longitud(f1)>longitud(f2)
Funcion frasemayorlongitud()
	Definir f1,f2 Como Caracter
	
	Escribir "Ingrese frese 1"
	Leer f1
	Escribir "Ingrese frase 2"
	Leer f2
	
	si Longitud(f1)>Longitud(f2) Entonces
		Escribir "La frase mayor o con mas longitud es: ",f1
	SiNo
		Escribir "La frase mayor o con mas longitud es: ",f2
	FinSi
FinFuncion

//frase="Hola, que tal; como te va,Bien: y tu, como estas."
// ,=3  .=1  ;=1 :1   si subcadena(frase,pos,pos)=","

Funcion indicarcuantospuntosetchay()
	Definir frase Como Caracter
	Definir lon,pos,cca Como Entero
	c=1
	cca=0
	pos=0
	lon=Longitud(frase) 
	Escribir "Ingrese frase"
	Leer frase
	
	Para pos=0 Hasta Longitud(frase) Con Paso 1 Hacer
		si Subcadena(frase,pos,pos)="," o Subcadena(frase,pos,pos)="." o Subcadena(frase,pos,pos)=";" o Subcadena(frase,pos,pos)=":" Entonces
			cca=cca+1
			//Mostrar cca
		FinSi
	FinPara
	Mostrar "La cantidad de ,.;: es de: ",cca
FinFuncion

//frase="Juan tiene 20 dolares"
// vocales=8   consonantes=8 digitos=2  si subcadena(frase,pos,pos)>="0" y <="9"

Funcion idicardorvocadigiconso()
	Definir texto Como Caracter
	Definir lon,pos,cv,cs,cd Como Entero
	pos=0
	cv=0
	cs=0
	cd=0
	Escribir "Ingrese texto"
	Leer texto
	Para pos=0 Hasta Longitud(texto) Con Paso 1 Hacer
		si Subcadena(texto,pos,pos)="a" o Subcadena(texto,pos,pos)="e"  o Subcadena(texto,pos,pos)="i" o Subcadena(texto,pos,pos)="o"  o Subcadena(texto,pos,pos)="u" Entonces
			cv=cv+1
			//Mostrar cv
		FinSi
		si Subcadena(texto,pos,pos)="b" o Subcadena(texto,pos,pos)="c" o Subcadena(texto,pos,pos)="d" o Subcadena(texto,pos,pos)="f" o Subcadena(texto,pos,pos)="g" o Subcadena(texto,pos,pos)="h" o Subcadena(texto,pos,pos)="j" o Subcadena(texto,pos,pos)="k" o Subcadena(texto,pos,pos)="l" o Subcadena(texto,pos,pos)="m" o Subcadena(texto,pos,pos)="n" o Subcadena(texto,pos,pos)="ñ" o Subcadena(texto,pos,pos)="p" o Subcadena(texto,pos,pos)="q" o Subcadena(texto,pos,pos)="r" o Subcadena(texto,pos,pos)="s" o Subcadena(texto,pos,pos)="t" o Subcadena(texto,pos,pos)="v" o Subcadena(texto,pos,pos)="w" o Subcadena(texto,pos,pos)="x" o Subcadena(texto,pos,pos)="y" o Subcadena(texto,pos,pos)="z" Entonces
			cs=cs+1
			//Mostrar cs
		FinSi
		si Subcadena(texto,pos,pos)>="0" y Subcadena(texto,pos,pos)<="9" Entonces
			cd=cd+1
			//Mostrar cd
		FinSi
	FinPara
	Mostrar "la cantidad de vocales son....",cv
	Mostrar "la cantidad de consonantes son....",cs
	Mostrar "la cantidad de digitos son....",cd
FinFuncion

// frase = "hola   que  tal" palabras=3
Funcion cuantaspalabrashay()
	Definir frase Como Caracter
	Definir lon,pos Como Entero
	pos=0
	cp=1
	lon=Longitud(frase)
	
	Escribir "Ingrese frase: "
	Leer frase
	
	Para pos=0 Hasta Longitud(frase) Con Paso 1 Hacer
		//cf=cf+1
		//Mostrar cf
		si Subcadena(frase,pos,pos)==" " y Subcadena(frase,pos-1,pos-1)<>" " Entonces
			cp=cp+1
			//Mostrar cp
		FinSi
		c=c+1
	FinPara
	Mostrar "La cantidad de palabras es..... ", cp
FinFuncion

// cedula="0914192182"= 37   convertirANumero(subcadena(frase,pos,pos))
Funcion sumadigitosingre()
	Definir cedula Como caracter
	Definir lon,pos Como Entero
	pos=0
	suma=0
	Escribir "Ingrese cedula"
	Leer cedula
	Para pos=0 Hasta longitud(cedula) Con Paso 1 Hacer
		suma=suma+ConvertirANumero(Subcadena(cedula,pos,pos))
		//Mostrar suma
	FinPara
	Mostrar "La suma de los digitos de su cedula es.... ",suma
FinFuncion

// palabra="ana"
Funcion palabrapalindroma()
	Definir palabra Como Caracter
	Definir i,j Como Entero
	
	Escribir "Ingrese la palabra"
	Leer palabra
	
	j=longitud(palabra)
	Para i=1 Hasta longitud(palabra) Hacer
		j=j-1
		inversa=inversa+Subcadena(palabra,j,j)
		//Mostrar j
		//Mostrar inversa
	FinPara
	si (palabra = inversa) Entonces
		escribir("La palabra es un palíndroma.")
	sino
		escribir("La palabra no es un palíndroma.")
	FinSi
FinFuncion

//Presentar la posicion de un caracter o subcadena cualquiera dentro de una cadena
// cadena="hola que tal"
//         01234567891011
//caracter="qui"  resp=-1
//caracter="que"  resp=5

Funcion indicarposcicion()
	definir frase,carter Como caracter
	Definir i Como Entero
	i=0
	Escribir "Ingrese una frase"
	Leer frase
	Escribir "Ingrese el caracter que le gustaria buscar"
	Leer carter
	
	Para i=1 Hasta Longitud(frase) con paso 1 Hacer
		result=Subcadena(frase,i,i)
		//Mostrar result
		//Mostrar i
		si carter=result Entonces
			Mostrar "Ese caracter esta en la posicion.... ",i
		FinSi
	FinPara
FinFuncion

// Ejercicios arreglos
// Ingresar 10 numeros y presentar cada numero del arreglo 1 por 1
Funcion numero1x1()
	Dimension numeros[100]
	Para i<-1 Hasta 10 Hacer
		Escribir 'Escriba 10 numeros maximos del 1 al 100 '
		Leer numeros[i]
	FinPara
	Para i<-1 Hasta 10 Hacer
	Escribir numeros[i] Sin Saltar
	FinPara
FinFuncion

// arreglo=[2,3,4,67,8] presenta 2 4 8 
Funcion arreglopares()
	Definir num Como Entero
	Dimension num[50]
	
	i=1
	Para i=1 Hasta 5 Hacer
		Escribir "Ingrese 5 numeros"," Numero: ",i
		Leer num[i]
	FinPara
	para i=1 Hasta 5 Hacer
		si num[i] mod 2=0 Entonces
			Mostrar "El arreglo ",i, " es un numero par: ",num[i]
		FinSi
		c=c+1
	FinPara
FinFuncion

// 2,4,-6,2,-5 = [-6,-5]  = presenta -6 -5
Funcion presentarnumeronegativos()
	Definir num Como Entero
	Dimension num[50]
	
	i=1
	
	Para i=1 Hasta 5 Hacer
		Escribir "Ingrese 5 numeros"," Numero: ",i
		Leer num[i]
	FinPara
	Para i=1 Hasta 5 Hacer
		si num[i]<=0 Entonces
			Mostrar "El arreglo ",i," es un numero negativo: ",num[i]
		FinSi
		c=c+1
	FinPara
FinFuncion

// n=3
// ["ana","jose","dan"]  presenta a j d 
Funcion caracterdelprimernumero()
	Definir nomb, p, ci Como caracter
	Definir Cnom Como Entero
	Dimension nomb[10]
	Dimension acu[10]
	c = 1
	l = "f"
	Escribir "Ingresa la cantidad de nombres"
	leer Cnom
	
	Mientras c <= Cnom Hacer
		Escribir "Ingrese nombre " Sin Saltar
		Leer nomb[c] 
		ci=Subcadena(nomb[c],i,i)
		si ci<>l Entonces
			acu[c] = ci
		FinSi
		c=c+1
	FinMientras
	para c = 1 hasta Cnom con paso 1 Hacer
		Mostrar " [ ",acu[c] " ] " Sin Saltar
	FinPara
FinFuncion

//n=5  arreglo=[10,20,30,5,10]= total=75  cant=5   prom=15  
//Dado un arreglo de numeros presentar el total, la cantidad y el promedio del arreglo
Funcion cantidadtotalypromedio()
	Definir num,totnum Como Entero
	Dimension num[50]
	
	Escribir "Ingrese el total de numeros a ingresar"
	Leer totnum
	Para i=1 Hasta totnum Con Paso 1 Hacer
		Escribir "Ingrese los numeros ", " Numero: ",i
		Leer num[i]
		acu=acu+num[i]
	FinPara
	Para i=1 Hasta totnum Hacer
		prom=acu/totnum
	FinPara
	Mostrar "El total de numeros es: ",acu
	Mostrar "La cantidad de numeros es: ",totnum
	Mostrar "El promedio es de: ",prom
FinFuncion

//n=5  arreglo=[8,20,7,5,4] presenta 5 20
Funcion multiplosyalreves()
	Definir num,totnum Como Entero
	Dimension num[50]
	Escribir "Ingrese el total de numeros a ingresar"
	Leer totnum
	
	Para i=1 Hasta totnum Con Paso 1 Hacer
		Escribir "Ingrese los numeros "," Numero: ",i
		Leer num[i]
	FinPara
	Para i=totnum Hasta 1 Con Paso -1 Hacer
		si num[i] mod 5 = 0 Entonces
			Mostrar "Los numeros del arreglo al revez multiplos de 5 son: ",num[i]
		FinSi
	FinPara
FinFuncion

//n=5  arreglo=[8,20,7,5,4] presenta 8  7  4
//7)Dado un arreglo presentar el primero,el medio y el ultimo elemento del arreglo

Funcion primeromedioultimo()
	Definir num,totnum Como Entero
	Dimension num[50]
	Dimension num2[50]
	
	Escribir "Ingrese el total de numeros a ingresar"
	Leer totnum
	
	Para i=1 Hasta totnum Con Paso 1 Hacer
		Escribir "Ingrese los numeros "," Numero: ",i
		Leer num[i]
	FinPara
	Para i=1 Hasta totnum Con Paso 2 Hacer
		Mostrar " [ " num[i], " ] " Sin Saltar
	FinPara
FinFuncion

//n=5  arreglo1=[8,20,7,5,4]   arreglo2=[8,20,7,5,4] presenta 8,20,7,5,4
//"8)Dado un arreglo copiarlo en otro y presentarlo"
Funcion presentarenotroarreglo()
	Definir num,num2,totnum Como Entero
	Dimension num[50]
	Dimension num2[50]
	
	Para i=1 Hasta 5 Con Paso 1 Hacer
		Escribir "Ingrese 5 numeros "," Numero: ",i
		Leer num[i]
		num2[i]=num[i]
	FinPara
	Para i= 1 Hasta 5 Hacer
		Mostrar " [ " num2[i], " ] " Sin Saltar
	FinPara
FinFuncion

//9)Dado 2 arreglos copiar en un otroarreglo la suma de cada elemento de los 2 arreglos
//n=5  arreglo1=[8,20,7,5,4]
//     arreglo2=[2,1,3,5,6] copiarArreglo3=[pos]=arreglo1[pos]+arreglo2[pos]

Funcion dosarreglossuma()
	Definir num,num2,suma1,suma2,sumatot Como Entero
	Dimension num[50]
	Dimension num2[50]
	//Dimension num3[50]
	Dimension sumatot[50]
	
	Para i=1 Hasta 5 Con Paso 1 Hacer
		Escribir "Ingrese 5  numeros del primer arreglo "," Numero: ",i
		Leer num[i]
		suma1=suma1+num[i]
		//Mostrar suma1
	FinPara
	Para i=1 Hasta 5 Con Paso 1 Hacer
		Escribir "Ingrese 5  numeros del segundo arreglo "," Numero: ",i
		Leer num2[i]
		suma2=suma2+num2[i]
		//Mostrar suma2
	FinPara
	Para i=1 Hasta 5 Con Paso 1 Hacer
		sumatot[i]=num[i]+num2[i]
		//Mostrar sumatot[i] ","
	FinPara
	Mostrar "la suma del primer arreglo es  "," [ " suma1 " ] "
	Mostrar "la suma del segundo arreglo es  "," [ " suma2 " ] "
FinFuncion

//n=5  3,2,1,5,4  arregloFactorual [6,2,1,120,24] 
//10)Dado una serie de numeros guarda en un arreglo los factoriales
Funcion factoriales()
	Definir num,facto,n Como Entero
	Dimension facto[50]
	
	Para i=1 Hasta 5 Con Paso 1 Hacer
		Escribir "Ingrese 5  numeros del segundo arreglo "," Numero: ",i
		Leer num
		n=num
		Mientras n > 1 Hacer
			n = n - 1
			num= num * n
		FinMientras
		facto[i] = num
	FinPara
	Escribir ""
	para i = 1 hasta 5 con paso 1 Hacer
		Mostrar facto[i]," , " Sin Saltar
	FinPara
FinFuncion

// Algoritmo principal del proyecto
Algoritmo Proyecto
	Definir menuPrincipal,menuNumeros,menuCadenas,menuArreglos,titulo,titulo2,opc,opcn,apcc,apca Como Caracter
	Definir pos,lim Como Entero
	Dimension menuPrincipal[4],menuNumeros[11],menuCadenas[11],menuArreglos[11]
	// qrreglo menu principal
	menuPrincipal[0] <- '  1)Ejercicios con Numeros'
	menuPrincipal[1] <- '  2)Ejercicios con Cadenas'
	menuPrincipal[2] <- '  3)Ejercicios con Arreglos'
	menuPrincipal[3] <- '  4)Salir'
	// arreglo submenu numeros
	menuNumeros[0] <- '  1)Mayor de 2 Numeros'
	menuNumeros[1] <- '  2)Dividir dos numeros por restas'
	menuNumeros[2] <- '  3)Multiplicar dos numeros por sumas'
	menuNumeros[3] <- '  4)Suma Pares y Productos multiplos de 5 de una secuencia de numeros'
	menuNumeros[4] <- '  5)Presentar cantidad de digitos de todos los numeros de una secuencia de numeros hasta 0'
	menuNumeros[5] <- '  6)Mostrar El Precio, descuento, iva y pago de n trajes del amacen SomosMas'
	menuNumeros[6] <- '  7)Dado tres numeros indicar si el segundo es el mayor'
	menuNumeros[7] <- '  8)Dado una secuencia de numeros presentar su promedio'
	menuNumeros[8] <- '  9)Numeros amigos'
	menuNumeros[9] <- '  10)primos gemelos'
	menuNumeros[10] <- '  11)Salir'
	// arreglos submenu cadenas
	menuCadenas[0] <- '  1)Ingresar un nombre y presentar el nombre carácter x caracter'
	menuCadenas[1] <- '  2)Presentar el primero, el medio y el ultimo caracter de una frase'
	menuCadenas[2] <- '  3)Dado dos nombres indicar si son iguales'
	menuCadenas[3] <- '  4)Dadas dos frase indicar la de mayor longitud'
	menuCadenas[4] <- '  5)Indicar cuantas ,.;: hay en una cadena'
	menuCadenas[5] <- '  6)Dado una cadena indicar cuantas vocales, consonantes y digitos hay'
	menuCadenas[6] <- '  7)Indicar cuantas palabras hay en una frase asumiendo 1 o varios espacios entre palabra'
	menuCadenas[7] <- '  8)Presentar la suma de los digitos de una cedula'
	menuCadenas[8] <- '  9)Indicar si una palabra es palindroma'
	menuCadenas[9] <- '  10)Presentar la posicion de un caracter o subcadena cualquiera dentro de una cadena'
	menuCadenas[10] <- '  11)Salir'
	// arreglo submenu arreglos
	menuArreglos[0] <- '	 1)Ingresar 10 numeros y presentar cada numero del arreglo 1 x 1'
	menuArreglos[1] <- '  2)Presentar los numeros pares de un arreglo'
	menuArreglos[2] <- '  3)Dado una serie de numeros guardar en un arreglo solo los numeros negativos'
	menuArreglos[3] <- '  4)Dado un arreglo de nombres presentar el primer caracter de cada nombre'
	menuArreglos[4] <- '  5)Dado un arreglo de numeros presentar el total, la cantidad y el promedio del arreglo'
	menuArreglos[5] <- '  6)Dado un arreglo presentarlo al revez solo los numeros multiplos de 5'
	menuArreglos[6] <- '  7)Dado un arreglo presentar el primero,el medio y el ultimo elemento del arreglo'
	menuArreglos[7] <- '  8)Dado un arreglo copiarlo en otro y presentarlo'
	menuArreglos[8] <- '  9)Dado 2 arreglos copiar en un otroarreglo la suma de cada elemento de los 2 arreglos'
	menuArreglos[9] <- '  10)Dado una serie de numeros guarda en un arreglo los factoriales'
	menuArreglos[10] <- '	 11) Salir'
	opc <- ''
	Mientras opc<>'4' Hacer
		opc <- presentarMenu('------ Menu Principal -------',menuPrincipal,4)
		Segun opc  Hacer
			'1':
				opcn <- ''
				Mientras opcn<>'11' Hacer
					opcn <- presentarMenu('------ Menu Numeros -------',menuNumeros,11)
					Segun opcn  Hacer
						'1':
							Escribir 'Mayor de dos Numeros'
							mayorDosNumeros()
							Esperar 3 Segundos
						'2':
							Escribir 'Dividir un numero mediante Resta'
							dividirDosNumerosResta()
							Esperar 3 Segundos
						'3':
							Escribir 'Multiplicar 2 numeros mediante suma'
							MultiDosNumerosSuma()
							Esperar 3 Segundos
						'4':
							Escribir '4)Suma Pares y Productos multiplos de 5 de una secuencia de numeros'
							Sumaparesymultiplosde5()
							Esperar 3 Segundos
						'5':
							Escribir '5)Presentar cantidad de digitos de todos los numeros de una secuencia de numeros hasta 0'
							secuencianum()
							Esperar 3 Segundos
						'6':
							Escribir '6)Mostrar El Precio, descuento, iva y pago de n trajes del amacen SomosMas'
							promocionalmacen()
							Esperar 3 Segundos
						'7':
							Escribir '7)Dado tres numeros indicar si el segundo es el mayor'
							mayornumeros()
							Esperar 3 Segundos
						'8':
							Escribir '8)Dado una secuencia de numeros presentar su promedio'
							promediosecuencia()
							Esperar 3 Segundos
						'9':
							Escribir '9)Numeros amigos'
							numerosamigos()
							Esperar 3 Segundos
						'10':
							Escribir '10)primos gemelos'
							primosgemelos()
							Esperar 3 Segundos
						'11':
							Escribir 'Regresando al Menu Principal'
							Esperar 3 Segundos
						De Otro Modo:
							Escribir 'Opcion invalidad...'
							Esperar 3 Segundos
					FinSegun
				FinMientras
			'2':
				opcc <- ''
				Mientras opcc<>'11' Hacer
					opcc <- presentarMenu('------ Menu Cadenas -------',menuCadenas,11)
					Segun opcc  Hacer
						'1':
							Escribir 'Ingresar un nombre y presentar el nombre carácter x caracter'
							nombreCaracter()
							Esperar 3 Segundos
						'2':
							Escribir '2)Presentar el primero, el medio y el ultimo caracter de una frase'
							primermedioyultimo()
							Esperar 3 Segundos
						'3':
							Escribir '3)Dado dos nombres indicar si son iguales'
							nombreigual()
							Esperar 3 Segundos
						'4':
							Escribir '4)Dadas dos frase indicar la de mayor longitud'
							frasemayorlongitud
							Esperar 3 Segundos
						'5':
							Escribir '5)Indicar cuantas ,.;: hay en una cadena'
							indicarcuantospuntosetchay()
							Esperar 3 Segundos
						'6':
							Escribir '6)Dado una cadena indicar cuantas vocales, consonantes y digitos hay'
							idicardorvocadigiconso()
							Esperar 3 Segundos
						'7':
							Escribir '7)Indicar cuantas palabras hay en una frase asumiendo 1 o varios espacios entre palabra'
							cuantaspalabrashay()
							Esperar 3 Segundos
						'8':
							Escribir '8)Presentar la suma de los digitos de una cedula'
							sumadigitosingre()
							Esperar 3 Segundos
						'9':
							Escribir '9)Indicar si una palabra es palindroma'
							palabrapalindroma()
							Esperar 3 Segundos
						'10':
							Escribir '10)Presentar la posicion de un caracter o subcadena cualquiera dentro de una cadena'
							indicarposcicion()
							Esperar 3 Segundos
						'11':
							Escribir 'Regresando al Menu Principal'
							Esperar 3 Segundos
						De Otro Modo:
							Escribir 'Opcion invalidad...'
							Esperar 3 Segundos
					FinSegun
				FinMientras
			'3':
				opca <- ''
				Mientras opca<>'11' Hacer
					opca <- presentarMenu('------ Menu Arreglos ------',menuArreglos,11)
					Segun opca  Hacer
						'1':
							Escribir '1)Ingresar 10 numeros y presentar cada numero del arreglo 1 x 1'
							numero1x1()
							Esperar 3 Segundos
						'2':
							Escribir '2)Presentar los numeros pares de un arreglo'
							arreglopares()
							Esperar 3 Segundos
						'3':
							Escribir '3)Dado una serie de numeros guardar en un arreglo solo los numeros negativos'
							presentarnumeronegativos()
							Esperar 3 Segundos
						'4':
							Escribir '4)Dado un arreglo de nombres presentar el primer caracter de cada nombre'
							caracterdelprimernumero()
							Esperar 3 Segundos
						'5':
							Escribir '5)Dado un arreglo de numeros presentar el total, la cantidad y el promedio del arreglo'
							cantidadtotalypromedio()
							Esperar 3 Segundos
						'6':
							Escribir '6)Dado un arreglo presentarlo al revez solo los numeros multiplos de 5'
							multiplosyalreves()
							Esperar 3 Segundos
						'7':
							Escribir '7)Dado un arreglo presentar el primero,el medio y el ultimo elemento del arreglo'
							primeromedioultimo()
							Esperar 3 Segundos
						'8':
							Escribir '8)Dado un arreglo copiarlo en otro y presentarlo'
							presentarenotroarreglo()
							Esperar 3 Segundos
						'9':
							Escribir '9)Dado 2 arreglos copiar en un otroarreglo la suma de cada elemento de los 2 arreglos'
							dosarreglossuma()
							Esperar 3 Segundos
						'10':
							Escribir '10)Dado una serie de numeros guarda en un arreglo los factoriales'
							factoriales()
							Esperar 300 Segundos
						'11':
							Escribir 'Regresando al Menu Principal'
							Esperar 3 Segundos
						De Otro Modo:
							Escribir 'Opcion invalidad...'
							Esperar 3 Segundos
					FinSegun
				FinMientras
			'4':
				Escribir 'Gracias por usar el Sistema'
				Esperar 3 Segundos
		FinSegun
	FinMientras
FinAlgoritmo
