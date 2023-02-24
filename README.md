program Proyecto;
uses crt;
var
comprar,boletos,cedula,metododeviaje,linea,salida,destino,verificarcompra,menu,menu2,cedula2,clave,repeticiones: longint;
pago,vuelto,montoapagar:integer;
nombre_apellido,tipo_boleto,transporte,lineaelegida: string;
estaciondesalida,estaciondedestino: string;

{ la clave es 1234}
				begin
				clrscr;
				Writeln('|================= Hola Ciudadano =================|');
				writeln('|--------------------------------------------------|');
				Writeln('|  Bienvenidos a la Estacion del Metro de Caracas  |');
				writeln('|--------------------------------------------------|');
				Writeln('|Si desea comprar un boleto, presione (1).         |');
				Writeln('|Si no desea comprar un boleto, presione (2).      |');
				writeln('|--------------------------------------------------|');
				Writeln('|==================================================|');
				Write  ('|---> ');
					readln(comprar);
				Writeln('|==================================================|');
while (comprar <> 1) and (comprar <> 2) do
			begin
				write('Por favor elige una opcion en pantalla : '); 
					readln(comprar);
			end;


		case comprar of
1: begin
				writeln('|--------------------------------------------------------------|');
				writeln('| Ingrese su nombre, apellido y cedula para empezar su compra. |');
				writeln('|--------------------------------------------------------------|');
				write  ('|Nombre y Apellido: ');
					readln(nombre_apellido);
				write  ('|Cedula: ');
					readln(cedula);
				Writeln('|==============================================================|');
				clrscr;
						Writeln('|=====================================================================================================|');
						Writeln('                                         Bienvenido ',(nombre_apellido),'                                     ');
						writeln('|=========================== Seleccione el tipo de boleto que desea comprar ==========================|');
						Writeln('|=====================================================================================================|');
						writeln('|Boleto          ','                Color          ','Cobertura','                                       Precio|');
						writeln('|-----------------------------------------------------------------------------------------------------|');
						writeln('|a. Simple       ','                Amarillo       ','1 Viaje en metro -------------------------------(5$)  |');
						writeln('|                                                                                                     |');
						Writeln('|b. Integrado    ','                Amarillo       ','1 Viaje en metro y  1 Viaje en metrobus --------(10$) |');
						writeln('|                                                                                                     |');
						writeln('|c. Ida y vuelta ','                Amarillo       ','2 Viajes en metro ------------------------------(15$) |');
						writeln('|                                                                                                     |');
						Writeln('|d. Ida y vuelta integrado','       Amarillo','       2 Viajes en metro y 2 en metrobus --------------(20$) |');
						writeln('|                                                                                                     |');
						writeln('|e. MultiAbono   ','                Naranja        ','10 Viajes en metro -----------------------------(25$) |');
						writeln('|                                                                                                     |');
						writeln('|f. Multiabono Integrado  ','       Naranja ','       10 Viajes en metro y 10 Viajes en metrobus -----(30$) |');
						writeln('|                                                                                                     |');
						writeln('|g. Estudiantil Simple    ','       Azul    ','       10 Viajes en metro -----------------------------(35$) |');
						writeln('|                                                                                                     |');
						writeln('|h. Estudiantil Integrado ','       Azul    ','       10 Viajes en metro y 20 Viajes en metrobus -----(40$) |');
						writeln('|                                                                                                     |');
						Writeln('|i. MetroTarjeta          ','       Rojo    ','       20, 30 y 40 Viajes (Metro y MetroBus) ----------(45$) |');
						writeln('|                                                                                                     |');
						Writeln('|j. Metro tarjeta Integrada','      Rojo    ','       20, 30 y 40 Viajes (Metro y MetroBus) ----------(50$) |');
						Writeln('|=====================================================================================================|');
						write('Introduce el tipo de boleto que desea comprar: ');
							readln(tipo_boleto); while (tipo_boleto <> 'a') and (tipo_boleto <> 'b') and (tipo_boleto <> 'c') 
	and (tipo_boleto <> 'd') and (tipo_boleto <> 'e') and (tipo_boleto <> 'f') and (tipo_boleto <> 'g') and (tipo_boleto <> 'h') 
	and (tipo_boleto <> 'i') and (tipo_boleto <> 'j') do
	
		begin
				write('Por favor ingrese algun tipo de boleto que se muestra en pantalla: '); readln(tipo_boleto);
		end;

					write('Cantidad de boletos a comprar: ');
							readln(boletos);
		
clrscr;
case tipo_boleto of
					'a': Begin writeln('=================================================================');
							   writeln('|A.Simple|    ','|Color : Amarillo| ',' |Cobertura: 1 Viaje en metro|');
							   writeln('|PRECIO| ', 'Cantidad de boletos comprados: ', (boletos),' |Total| ',boletos,' X ','5$ ', '= ', boletos*5,'$');
							   writeln('=================================================================');
							   montoapagar := boletos*5;
							   Writeln;
							   writeln('==================================');
							   writeln('Has seleccionado el viaje en metro');
							   writeln('==================================');
							   transporte := '"Viaje en metro"';
							   end;
           
					'b': Begin writeln('==============================================================================================');
							   writeln('|B.Integrado|    ','|Color : Amarillo| ',' |Cobertura: 1 Viaje en metro y 1 Viaje en metrobus|');
							   writeln('|PRECIO| ', 'Cantidad de boletos comprados: ', (boletos),' |Total| ',boletos,' X ','10$ ', '= ', boletos*10,'$');
							   writeln('==============================================================================================');
							   montoapagar := boletos*10;
							   writeln;
							   writeln('===================================');
							   writeln('En que metodo deseas viajar?');
							   writeln('Presione (1) para Viaje en metro');
							   writeln('Presione (2) para Viaje en metrobus');
							   writeln('===================================');
							   write('---> '); readln(metododeviaje);
							   while (metododeviaje <> 1) and (metododeviaje <> 2) do
             
begin
				
				write('Por favor elige una opcion en pantalla : '); 
					readln(metododeviaje);
end;
				if metododeviaje = 1 then begin
				writeln('==================================');
				writeln('Has seleccionado el viaje en metro');
				writeln('==================================');
				if (metododeviaje = 1) then (transporte) := '"Viaje en metro"';
				end;
				if metododeviaje = 2 then begin
				writeln('=====================================');
				writeln('Has seleccionado el viaje en metrobus');
				writeln('=====================================');
				if (metododeviaje = 2) then (transporte) := '"Viaje en metrobus"';
				end;
                
           end;
'c': begin writeln('============================================================================');
           writeln('|C.Ida y Vuelta|    ','|Color : Amarillo| ',' |Cobertura: 2 Viajes en metro|');
           writeln('|PRECIO| ', 'Cantidad de boletos comprados: ', (boletos),' |Total| ',boletos,' X ','15$ ', '= ', boletos*15,'$');
           writeln('============================================================================');
           montoapagar := boletos*15;
           writeln;
           writeln('==================================');
		   writeln('Has seleccionado el viaje en metro');
		   writeln('==================================');
		   transporte := '"Viaje en metro"';
		   end;
				
'd': begin writeln('======================================================================================================');
           writeln('|D.Ida y Vuelta Integrado|    ','|Color : Amarillo| ',' |Cobertura: 2 Viajes en metro y 2 en metrobus|');
           writeln('|PRECIO| ', 'Cantidad de boletos comprados: ', (boletos),' |Total| ',boletos,' X ','20$ ', '= ', boletos*20,'$');
           writeln('======================================================================================================');
           montoapagar := boletos*20;
           Writeln;
           writeln('===================================');
           writeln('En que metodo deseas viajar?');
           writeln('Presione (1) para Viaje en metro');
           writeln('Presione (2) para Viaje en metrobus');
           writeln('===================================');
             write('---> '); readln(metododeviaje);
             while (metododeviaje <> 1) and (metododeviaje <> 2) do
begin
	write('Por favor elige una opcion en pantalla : '); 
		readln(metododeviaje);
 end;
				if metododeviaje = 1 then begin
				writeln('==================================');
				writeln('Has seleccionado el viaje en metro');
				writeln('==================================');
				if (metododeviaje = 1) then (transporte) := '"Viaje en metro"';
				end;
				if metododeviaje = 2 then begin
				writeln('=====================================');
				writeln('Has seleccionado el viaje en metrobus');
				writeln('=====================================');
				if (metododeviaje = 2) then (transporte) := '"Viaje en metrobus"';
				end;
             
		   end;
'e': Begin Writeln('==========================================================================');
           writeln('|E.MultiAbono|    ','|Color : Naranja| ',' |Cobertura: 10 Viajes en metro|');
           writeln('|PRECIO| ', 'Cantidad de boletos comprados: ', (boletos),' |Total| ',boletos,' X ','25$ ', '= ', boletos*25,'$');
           writeln('==========================================================================');
           montoapagar := boletos*25;
           writeln;
           writeln('==================================');
		   writeln('Has seleccionado el viaje en metro');
		   writeln('==================================');
           transporte := '"Viaje en metro"';
           end;
'f': Begin Writeln('============================================================================================================');
           writeln('|F.MultiAbono Integrado|    ','|Color : Naranja| ',' |Cobertura: 10 Viajes en metro y 10 Viajes en metrobus|');
           writeln('|PRECIO| ', 'Cantidad de boletos comprados: ', (boletos),' |Total| ',boletos,' X ','30$ ', '= ', boletos*30,'$');
           writeln('============================================================================================================');
           montoapagar := boletos*30;
           Writeln;
           writeln('===================================');
           writeln('En que metodo deseas viajar?');
           writeln('Presione (1) para Viaje en metro');
           writeln('Presione (2) para Viaje en metrobus');
           writeln('===================================');
             write('---> '); readln(metododeviaje);
             while (metododeviaje <> 1) and (metododeviaje <> 2) do
begin
	write('Por favor elige una opcion en pantalla : '); 
		readln(metododeviaje);
 end;
				if metododeviaje = 1 then begin
				writeln('==================================');
				writeln('Has seleccionado el viaje en metro');
				writeln('==================================');
				if (metododeviaje = 1) then (transporte) := '"Viaje en metro"';
				end;
				if metododeviaje = 2 then begin
				writeln('=====================================');
				writeln('Has seleccionado el viaje en metrobus');
				writeln('=====================================');
				if (metododeviaje = 2) then (transporte) := '"Viaje en metrobus"';
				end;
           
           end;
'g': Begin Writeln('===============================================================================');
           writeln('|G.Estudiantil Simple|    ','|Color : Azul| ',' |Cobertura: 10 Viajes en metro|');
           writeln('|PRECIO| ', 'Cantidad de boletos comprados: ', (boletos),' |Total| ',boletos,' X ','35$ ', '= ', boletos*35,'$');
           writeln('===============================================================================');
            montoapagar := boletos*35;
           writeln;
           writeln('==================================');
		   writeln('Has seleccionado el viaje en metro');
		   writeln('==================================');
		   transporte := '"Viaje en metro"';
           end;
'h': Begin Writeln('==========================================================================================================');
           writeln('|H.Estudiantil Integrado|    ','|Color : Azul| ',' |Cobertura: 10 Viajes en metro y 20 Viajes en metrobus|');
           writeln('|PRECIO| ', 'Cantidad de boletos comprados: ', (boletos),' |Total| ',boletos,' X ','40$ ', '= ', boletos*40,'$');
           writeln('==========================================================================================================');
           montoapagar := boletos*40;
           Writeln;
           writeln('===================================');
           writeln('En que metodo deseas viajar?');
           writeln('Presione (1) para Viaje en metro');
           writeln('Presione (2) para Viaje en metrobus');
           writeln('===================================');
             write('---> '); readln(metododeviaje);
             while (metododeviaje <> 1) and (metododeviaje <> 2) do
begin
	write('Por favor elige una opcion en pantalla : '); 
		readln(metododeviaje);
 end;
				if metododeviaje = 1 then begin
				writeln('==================================');
				writeln('Has seleccionado el viaje en metro');
				writeln('==================================');
				if (metododeviaje = 1) then (transporte) := '"Viaje en metro"';
				end;
				if metododeviaje = 2 then begin
				writeln('=====================================');
				writeln('Has seleccionado el viaje en metrobus');
				writeln('=====================================');
				if (metododeviaje = 2) then (transporte) := '"Viaje en metrobus"';
				end;
           end;
'i': Begin Writeln('=======================================================================================');
           writeln('|I.MetroTarjeta|    ','|Color : Rojo| ',' |Cobertura: 20 Viajes, 30 Viajes y 40 Viajes|');
           writeln('|PRECIO| ', 'Cantidad de boletos comprados: ', (boletos),' |Total| ',boletos,' X ','45$ ', '= ', boletos*45,'$');
           writeln('=======================================================================================');
           montoapagar := boletos*45;
           Writeln;
           writeln('===================================');
           writeln('En que metodo deseas viajar?');
           writeln('Presione (1) para 20 Viajes (Metro y MetroBus)');
           writeln('Presione (2) para 30 Viajes (Metro y MetroBus)');
           Writeln('Presione (3) para 40 Viajes (Metro y MetroBus)');
           writeln('===================================');
             write('---> '); readln(metododeviaje);
             while (metododeviaje <> 1) and (metododeviaje <> 2) and (metododeviaje <> 3) do
begin
	write('Por favor elige una opcion en pantalla : '); 
		readln(metododeviaje);
 end;
				if metododeviaje = 1 then begin
				writeln('=============================================');
				writeln('Has seleccionado 20 Viajes (Metro y MetroBus)');
				writeln('=============================================');
				if (metododeviaje = 1) then (transporte) := '"20 (Metro y MetroBus)"';
				end;
				if metododeviaje = 2 then begin
				writeln('=============================================');
				writeln('Has seleccionado 30 Viajes (Metro y MetroBus)');
				writeln('=============================================');
				if (metododeviaje = 2) then (transporte) := '"30 (Metro y MetroBus)"';
				end;
				if metododeviaje = 3 then begin
				writeln('=============================================');
				writeln('Has seleccionado 40 Viajes (Metro y MetroBus)');
				writeln('=============================================');
				if (metododeviaje = 3) then (transporte) := '"40 (Metro y MetroBus)"';
				end;
           end;
'j': Begin Writeln('======================================================================================================');
           writeln('|J.MetroTarjeta Integrada|    ','|Color : Rojo| ',' |Cobertura: 20, 30 y 40 Viajes (Metro y MetroBus)|');
           writeln('|PRECIO| ', 'Cantidad de boletos comprados: ', (boletos),' |Total| ',boletos,' X ','50$ ', '= ', boletos*50,'$');
           writeln('======================================================================================================');
           montoapagar := boletos*50;
           Writeln;
           writeln('===================================');
           writeln('En que metodo deseas viajar?');
           writeln('Presione (1) para 20 Viajes (Metro y MetroBus)');
           writeln('Presione (2) para 30 Viajes (Metro y MetroBus)');
           Writeln('Presione (3) para 40 Viajes (Metro y MetroBus)');
           writeln('===================================');
             write('---> '); readln(metododeviaje);
             while (metododeviaje <> 1) and (metododeviaje <> 2) and (metododeviaje <> 3) do
begin
	write('Por favor elige una opcion en pantalla : '); 
		readln(metododeviaje);
 end;
				if metododeviaje = 1 then begin
				writeln('=============================================');
				writeln('Has seleccionado 20 Viajes (Metro y MetroBus)');
				writeln('=============================================');
				if (metododeviaje = 1) then (transporte) := '"20 (Metro y MetroBus)"';
				end;
				if metododeviaje = 2 then begin
				writeln('=============================================');
				writeln('Has seleccionado 30 Viajes (Metro y MetroBus)');
				writeln('=============================================');
				if (metododeviaje = 2) then (transporte) := '"30 (Metro y MetroBus)"';
				end;
				if metododeviaje = 3 then begin
				writeln('=============================================');
				writeln('Has seleccionado 40 Viajes (Metro y MetroBus)');
				writeln('=============================================');
				if (metododeviaje = 3) then (transporte) := '"40 (Metro y MetroBus)"';
				end;
           end;
          
end;
		writeln;
		writeln('===========================');
		writeln('Para avanzar presione enter');
		writeln('===========================');
			readln;
clrscr;

		writeln('|===========================================|');
		writeln('|Seleccione la linea en la que desea viajar |');
		writeln('|===========================================|');
		writeln('| Presione (1) para viajar por la "LINEA 1" |');
		writeln('|-------------------------------------------|');
		writeln('| Presione (2) para viajar por la "LINEA 2" |');
		writeln('|-------------------------------------------|');
		writeln('| Presione (3) para viajar por la "LINEA 3" |');
		writeln('|-------------------------------------------|'); 
		writeln('| Presione (4) para viajar por la "LINEA 4" |');
		writeln('|-------------------------------------------|');
		writeln('| Presione (5) para viajar por la "LINEA 5" |');
		writeln('|-------------------------------------------|');
		writeln('| Presione (6) para viajar por la "LINEA 6" |');
		writeln('|-------------------------------------------|');
		writeln('| Presione (7) para viajar por la "LINEA 7" |');
		writeln('|-------------------------------------------|');
		writeln('| Presione (8) para viajar por la "LINEA" 8 |');
		writeln('|===========================================|');
		Write('---> ');
		readln(linea);
	while (linea  <>  1)  and   (linea  <>  2) and  (linea  <>  3)  
	and  (linea  <>  4)  and  (linea  <>  5)  and  (linea  <>  6)  and  (linea  <>  7)  and  (linea  <>  8)  do
begin
write('Por favor elige una opcion en pantalla : '); 
		readln(linea);
end; 
clrscr;

	case linea of
1: begin
for repeticiones:= 1 to boletos do
begin
if linea = 1 then lineaelegida := ' LINEA 1 ';
		writeln ('|====================================== LINEA 1 =====================================|');
		writeln ('|====================================================================================|');
		writeln ('|(1)-Propatria       (2)-Capitolio         (3)-Plaza Venezuela   (4)-Miranda         |');
		writeln ('|(5)-Perez bonalde   (6)-La Hoyada         (7)-Sabana Grande     (8)-Los Dos Caminos |');
		writeln ('|(9)-Plaza Sucre     (10)-Parque Carabobo  (11)-Chacaito         (12)-Los Cortijos   |');
		writeln ('|(13)-Gato Negro     (14)-Bellas Artes     (15)-Chacao           (16)-La california  |');
		writeln ('|(17)-Cano Amarillo  (18)-Colegio de ing.  (19)-Altamira         (20)-Petare         |');
		writeln ('|(21)-Agua Salud                                                 (22)-Palo Verde     |');
		writeln ('|====================================================================================|');
		   write('Seleccione sub estacion de SALIDA: '); readln(salida); 
		   if salida = 1 then begin 
		   estaciondesalida := estaciondesalida + ' Propatria '; end;
		   if salida = 2 then begin 
		   estaciondesalida := estaciondesalida + ' Capitolio '; end;
		   if salida = 3 then begin 
		   estaciondesalida := estaciondesalida + ' Plaza Venezuela '; end;
		   if salida = 4 then begin 
		   estaciondesalida := estaciondesalida + ' Miranda '; end;
		   if salida = 5 then begin 
		   estaciondesalida := estaciondesalida + ' Perez bonalde '; end;
		   if salida = 6 then begin 
		   estaciondesalida := estaciondesalida + ' La Hoyada '; end;
		   if salida = 7 then begin 
		   estaciondesalida := estaciondesalida + ' Sabana Grande '; end;
		   if salida = 8 then begin 
		   estaciondesalida := estaciondesalida + ' Los Dos Caminos '; end;
		   if salida = 9 then begin 
		   estaciondesalida := estaciondesalida + ' Plaza Sucre '; end;
		   if salida = 10 then begin 
		   estaciondesalida := estaciondesalida + ' Parque Carabobo '; end;
		   if salida = 11 then begin 
		   estaciondesalida := estaciondesalida + ' Chacaito '; end;
		   if salida = 12 then begin 
		   estaciondesalida := estaciondesalida + ' Los Cortijos '; end;
		   if salida = 13 then begin 
		   estaciondesalida := estaciondesalida + ' Gato Negro '; end;
		   if salida = 14 then begin 
		   estaciondesalida := estaciondesalida + ' Bellas Artes '; end;
		   if salida = 15 then begin 
		   estaciondesalida := estaciondesalida +' Chacao '; end;
		   if salida = 16 then begin 
		   estaciondesalida := estaciondesalida + ' La california '; end;
		   if salida = 17 then begin 
		   estaciondesalida := estaciondesalida + ' Cano Amarillo '; end;
		   if salida = 18 then begin 
		   estaciondesalida := estaciondesalida + ' Colegio de ing. '; end;
		   if salida = 19 then begin 
		   estaciondesalida := estaciondesalida + ' Altamira '; end;
		   if salida = 20 then begin 
		   estaciondesalida := estaciondesalida + ' Petare '; end;
		   if salida = 21 then begin 
		   estaciondesalida := estaciondesalida + ' Agua Salud '; end;
		   if salida = 22 then begin 
		   estaciondesalida := estaciondesalida + ' Palo Verde '; end;
		                    
				while (salida <> 1) and (salida <> 2) and (salida <> 3)  and (salida <> 4)  
				and (salida <> 5)  and (salida <> 6)  and (salida <> 7)  and (salida <> 8)  
				and (salida <> 9)  and (salida <> 10)  and (salida <> 11)  and (salida <> 12)  
				and (salida <> 13)  and (salida <> 14)  and (salida <> 15)  and (salida <> 16)  
				and (salida <> 17)  and (salida <> 18)  and (salida <> 19)  and (salida <> 20)  
				and (salida <> 21)  and (salida <> 22)  do
				
				
begin
		   write('Por favor elige una opcion en pantalla : '); 
		   readln(salida);
		   if salida = 1 then begin 
		   estaciondesalida := estaciondesalida + ' Propatria '; end;
		   if salida = 2 then begin 
		   estaciondesalida := estaciondesalida + ' Capitolio '; end;
		   if salida = 3 then begin 
		   estaciondesalida := estaciondesalida + ' Plaza Venezuela '; end;
		   if salida = 4 then begin 
		   estaciondesalida := estaciondesalida + ' Miranda '; end;
		   if salida = 5 then begin 
		   estaciondesalida := estaciondesalida + ' Perez bonalde '; end;
		   if salida = 6 then begin 
		   estaciondesalida := estaciondesalida + ' La Hoyada '; end;
		   if salida = 7 then begin 
		   estaciondesalida := estaciondesalida + ' Sabana Grande '; end;
		   if salida = 8 then begin 
		   estaciondesalida := estaciondesalida + ' Los Dos Caminos '; end;
		   if salida = 9 then begin 
		   estaciondesalida := estaciondesalida + ' Plaza Sucre '; end;
		   if salida = 10 then begin 
		   estaciondesalida := estaciondesalida + ' Parque Carabobo '; end;
		   if salida = 11 then begin 
		   estaciondesalida := estaciondesalida + ' Chacaito '; end;
		   if salida = 12 then begin 
		   estaciondesalida := estaciondesalida + ' Los Cortijos '; end;
		   if salida = 13 then begin 
		   estaciondesalida := estaciondesalida + ' Gato Negro '; end;
		   if salida = 14 then begin 
		   estaciondesalida := estaciondesalida + ' Bellas Artes '; end;
		   if salida = 15 then begin 
		   estaciondesalida := estaciondesalida +' Chacao '; end;
		   if salida = 16 then begin 
		   estaciondesalida := estaciondesalida + ' La california '; end;
		   if salida = 17 then begin 
		   estaciondesalida := estaciondesalida + ' Cano Amarillo '; end;
		   if salida = 18 then begin 
		   estaciondesalida := estaciondesalida + ' Colegio de ing. '; end;
		   if salida = 19 then begin 
		   estaciondesalida := estaciondesalida + ' Altamira '; end;
		   if salida = 20 then begin 
		   estaciondesalida := estaciondesalida + ' Petare '; end;
		   if salida = 21 then begin 
		   estaciondesalida := estaciondesalida + ' Agua Salud '; end;
		   if salida = 22 then begin 
		   estaciondesalida := estaciondesalida + ' Palo Verde '; end;
			end; 
		   write('Seleccione sub estacion de DESTINO: '); readln(destino); 
		   if destino = 1 then begin 
		   estaciondedestino := estaciondedestino  + ' Propatria '; end;
		   if destino  = 2 then begin 
		   estaciondedestino := estaciondedestino + ' Capitolio '; end;
		   if destino  = 3 then begin 
		   estaciondedestino := estaciondedestino + ' Plaza Venezuela '; end;
		   if destino = 4 then begin 
		   estaciondedestino := estaciondedestino + ' Miranda '; end;
		   if destino = 5 then begin 
		   estaciondedestino := estaciondedestino + ' Perez bonalde '; end;
		   if destino = 6 then begin 
		   estaciondedestino := estaciondedestino + ' La Hoyada '; end;
		   if destino = 7 then begin 
		   estaciondedestino := estaciondedestino + ' Sabana Grande '; end;
		   if destino = 8 then begin 
		   estaciondedestino := estaciondedestino+ ' Los Dos Caminos '; end;
		   if destino = 9 then begin 
		   estaciondedestino := estaciondedestino + ' Plaza Sucre '; end;
		   if destino = 10 then begin 
		   estaciondedestino := estaciondedestino + ' Parque Carabobo '; end;
		   if destino = 11 then begin 
		   estaciondedestino := estaciondedestino+ ' Chacaito '; end;
		   if destino = 12 then begin 
		   estaciondedestino:= estaciondedestino + ' Los Cortijos '; end;
		   if destino = 13 then begin 
		   estaciondedestino := estaciondedestino + ' Gato Negro '; end;
		   if destino = 14 then begin 
		   estaciondedestino := estaciondedestino + ' Bellas Artes '; end;
		   if destino = 15 then begin 
		   estaciondedestino := estaciondedestino +' Chacao '; end;
		   if destino = 16 then begin 
		   estaciondedestino := estaciondedestino + ' La california '; end;
		   if destino = 17 then begin 
		   estaciondedestino := estaciondedestino + ' Cano Amarillo '; end;
		   if destino = 18 then begin 
		   estaciondedestino := estaciondedestino + ' Colegio de ing. '; end;
		   if destino = 19 then begin 
		   estaciondedestino:= estaciondedestino + ' Altamira '; end;
		   if destino = 20 then begin 
		  estaciondedestino := estaciondedestino + ' Petare '; end;
		   if destino = 21 then begin 
		  estaciondedestino := estaciondedestino + ' Agua Salud '; end;
		   if destino = 22 then begin 
		   estaciondedestino := estaciondedestino + ' Palo Verde '; end;
				while (destino <> 1) and (destino <> 2) and (destino <> 3)  and (destino <> 4)  
				and (destino <> 5)  and (destino <> 6)  and (destino <> 7)  and (destino <> 8)  
				and (destino <> 9)  and (destino <> 10)  and (destino <> 11)  and (destino <> 12)  
				and (destino <> 13)  and (destino <> 14)  and (destino <> 15)  and (destino <> 16)  
				and (destino <> 17)  and (destino <> 18)  and (destino <> 19)  and (destino <> 20)  
				and (destino <> 21)  and (destino <> 22)  do
				
				
begin
           write('Por favor elige una opcion en pantalla : '); 
	       readln(destino);
	      if destino = 1 then begin 
		   estaciondedestino := estaciondedestino  + ' Propatria '; end;
		   if destino  = 2 then begin 
		   estaciondedestino := estaciondedestino + ' Capitolio '; end;
		   if destino  = 3 then begin 
		   estaciondedestino := estaciondedestino + ' Plaza Venezuela '; end;
		   if destino = 4 then begin 
		   estaciondedestino := estaciondedestino + ' Miranda '; end;
		   if destino = 5 then begin 
		   estaciondedestino := estaciondedestino + ' Perez bonalde '; end;
		   if destino = 6 then begin 
		   estaciondedestino := estaciondedestino + ' La Hoyada '; end;
		   if destino = 7 then begin 
		   estaciondedestino := estaciondedestino + ' Sabana Grande '; end;
		   if destino = 8 then begin 
		   estaciondedestino := estaciondedestino+ ' Los Dos Caminos '; end;
		   if destino = 9 then begin 
		   estaciondedestino := estaciondedestino + ' Plaza Sucre '; end;
		   if destino = 10 then begin 
		   estaciondedestino := estaciondedestino + ' Parque Carabobo '; end;
		   if destino = 11 then begin 
		   estaciondedestino := estaciondedestino+ ' Chacaito '; end;
		   if destino = 12 then begin 
		   estaciondedestino:= estaciondedestino + ' Los Cortijos '; end;
		   if destino = 13 then begin 
		   estaciondedestino := estaciondedestino + ' Gato Negro '; end;
		   if destino = 14 then begin 
		   estaciondedestino := estaciondedestino + ' Bellas Artes '; end;
		   if destino = 15 then begin 
		   estaciondedestino := estaciondedestino +' Chacao '; end;
		   if destino = 16 then begin 
		   estaciondedestino := estaciondedestino + ' La california '; end;
		   if destino = 17 then begin 
		   estaciondedestino := estaciondedestino + ' Cano Amarillo '; end;
		   if destino = 18 then begin 
		   estaciondedestino := estaciondedestino + ' Colegio de ing. '; end;
		   if destino = 19 then begin 
		   estaciondedestino:= estaciondedestino + ' Altamira '; end;
		   if destino = 20 then begin 
		  estaciondedestino := estaciondedestino + ' Petare '; end;
		   if destino = 21 then begin 
		  estaciondedestino := estaciondedestino + ' Agua Salud '; end;
		   if destino = 22 then begin 
		   estaciondedestino := estaciondedestino + ' Palo Verde '; end;
		   end;  

		end;
		end;
 2 : begin 
 for repeticiones:= 1 to boletos do
begin
 if linea = 2 then lineaelegida := ' LINEA 2 ';
		writeln ('|============================= LINEA 2 ============================|');
		writeln ('|==================================================================|');
		writeln ('|(1)-El Silencio   (2)-La Paz        (3)-Mamera                    |');
		writeln ('|(4)-Capuchinos    (5)-La Yaguara    (6)-Caricuao                  |');
		writeln ('|(7)-Maternidad    (8)-Carapita      (9)-Zoologico                 |');
		writeln ('|(10)-artiguas     (11)-Antimano     (12)-Ruiz Pineda/ Las adjuntas|');
		writeln ('|==================================================================|');
		write('Seleccione sub estacion de SALIDA: '); readln(salida);
		   if salida = 1 then begin estaciondesalida := estaciondesalida + ' El Silencio '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' La Paz '; end;
		   if salida = 3 then begin estaciondesalida := estaciondesalida + 'Mamera '; end;
		   if salida = 4 then begin estaciondesalida := estaciondesalida + ' Capuchinos '; end;
		   if salida = 5 then begin estaciondesalida := estaciondesalida + ' La Yaguara '; end;
		   if salida = 6 then begin estaciondesalida := estaciondesalida + ' Caricuao '; end;
		   if salida = 7 then begin estaciondesalida := estaciondesalida + ' Maternidad '; end;
		   if salida = 8 then begin estaciondesalida := estaciondesalida + ' Carapita '; end;
		   if salida = 9 then begin estaciondesalida := estaciondesalida + ' Zoologico '; end;
		   if salida = 10 then begin estaciondesalida := estaciondesalida + ' artiguas '; end;
		   if salida = 11 then begin estaciondesalida := estaciondesalida + ' Antimano '; end;
		   if salida = 12 then begin estaciondesalida := estaciondesalida + ' Ruiz Pineda/ Las adjuntas '; end;
		   
while (salida <> 1) and (salida <> 2) and (salida <> 3)  and (salida <> 4)  
and (salida <> 5)  and (salida <> 6)  and (salida <> 7)  and (salida <> 8)  
and (salida <> 9)  and (salida <> 10)  and (salida <> 11)  and (salida <> 12) do

begin
write('Por favor elige una opcion en pantalla : '); 
readln(salida);
		   if salida = 1 then begin estaciondesalida := estaciondesalida + ' El Silencio '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' La Paz '; end;
		   if salida = 3 then begin estaciondesalida := estaciondesalida + 'Mamera '; end;
		   if salida = 4 then begin estaciondesalida := estaciondesalida + ' Capuchinos '; end;
		   if salida = 5 then begin estaciondesalida := estaciondesalida + ' La Yaguara '; end;
		   if salida = 6 then begin estaciondesalida := estaciondesalida + ' Caricuao '; end;
		   if salida = 7 then begin estaciondesalida := estaciondesalida + ' Maternidad '; end;
		   if salida = 8 then begin estaciondesalida := estaciondesalida + ' Carapita '; end;
		   if salida = 9 then begin estaciondesalida := estaciondesalida + ' Zoologico '; end;
		   if salida = 10 then begin estaciondesalida := estaciondesalida + ' artiguas '; end;
		   if salida = 11 then begin estaciondesalida := estaciondesalida + ' Antimano '; end;
		   if salida = 12 then begin estaciondesalida := estaciondesalida + ' Ruiz Pineda/ Las adjuntas '; end;
 end; 
 write('Seleccione sub estacion de DESTINO: '); readln(destino);
 		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' El Silencio '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' La Paz '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' Mamera '; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' Capuchinos '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' La Yaguara '; end;
		   if destino = 6 then begin estaciondedestino := estaciondedestino + ' Caricuao '; end;
		   if destino = 7 then begin estaciondedestino := estaciondedestino + ' Maternidad '; end;
		   if destino = 8 then begin estaciondedestino := estaciondedestino + ' Carapita '; end;
		   if destino = 9 then begin estaciondedestino := estaciondedestino + ' Zoologico '; end;
		   if destino = 10 then begin estaciondedestino := estaciondedestino + ' artiguas '; end;
		   if destino = 11 then begin estaciondedestino := estaciondedestino + ' Antimano '; end;
		   if destino = 12 then begin estaciondedestino := estaciondedestino + ' Ruiz Pineda/ Las adjuntas '; end;
		   
while (destino <> 1) and (destino <> 2) and (destino <> 3)  and (destino <> 4)  
and (destino <> 5)  and (destino <> 6)  and (destino <> 7)  and (destino <> 8)  
and (destino <> 9)  and (destino <> 10)  and (destino <> 11)  and (destino <> 12)  do

begin
write('Por favor elige una opcion en pantalla : '); 
readln(destino);
 		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' El Silencio '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' La Paz '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' Mamera '; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' Capuchinos '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' La Yaguara '; end;
		   if destino = 6 then begin estaciondedestino := estaciondedestino + ' Caricuao '; end;
		   if destino = 7 then begin estaciondedestino := estaciondedestino + ' Maternidad '; end;
		   if destino = 8 then begin estaciondedestino := estaciondedestino + ' Carapita '; end;
		   if destino = 9 then begin estaciondedestino := estaciondedestino + ' Zoologico '; end;
		   if destino = 10 then begin estaciondedestino := estaciondedestino + ' artiguas '; end;
		   if destino = 11 then begin estaciondedestino := estaciondedestino + ' Antimano '; end;
		   if destino = 12 then begin estaciondedestino := estaciondedestino + ' Ruiz Pineda/ Las adjuntas '; end;
 end;  
		end;
 end;
 
3 : begin
for repeticiones:= 1 to boletos do
begin
 if linea = 3 then lineaelegida := ' LINEA 3 ';
		writeln ('|========================== LINEA 3 ==========================|');
		writeln ('|=============================================================|');
		writeln ('|(1)-Plaza Venezuela       (2)-La Bandera     (3)-Coche       |');
		writeln ('|(4)-Ciudad universitaria  (5)-El valle       (6)-Meracdo     |');
		writeln ('|(7)-Los simbolos          (8)-Los Jardines   (9)-La Rinconada|');
		writeln ('|=============================================================|');
		write('Seleccione sub estacion de SALIDA: '); readln(salida);
		   if salida = 1 then begin  estaciondesalida := estaciondesalida + ' Plaza Venezuela '; end;
		   if salida = 2 then begin  estaciondesalida := estaciondesalida + ' La Bandera '; end;
		   if salida = 3 then begin  estaciondesalida := estaciondesalida + ' Coche '; end;
		   if salida = 4 then begin  estaciondesalida := estaciondesalida + ' Ciudad universitaria '; end;
		   if salida = 5 then begin  estaciondesalida := estaciondesalida + ' El valle '; end;
		   if salida = 6 then begin  estaciondesalida := estaciondesalida + ' Meracdo '; end;
		   if salida = 7 then begin  estaciondesalida := estaciondesalida + ' Los simbolos '; end;
		   if salida = 8 then begin  estaciondesalida := estaciondesalida + ' Los Jardines '; end;
		   if salida = 9 then begin  estaciondesalida := estaciondesalida + ' La Rinconada '; end;
		   
while (salida <> 1) and (salida <> 2) and (salida <> 3)  and (salida <> 4)  
and (salida <> 5)  and (salida <> 6)  and (salida <> 7)  and (salida <> 8)  
and (salida <> 9) do

begin
write('Por favor elige una opcion en pantalla : '); 
readln(salida);
		   if salida = 1 then begin  estaciondesalida := estaciondesalida + ' Plaza Venezuela '; end;
		   if salida = 2 then begin  estaciondesalida := estaciondesalida + ' La Bandera '; end;
		   if salida = 3 then begin  estaciondesalida := estaciondesalida + ' Coche '; end;
		   if salida = 4 then begin  estaciondesalida := estaciondesalida + ' Ciudad universitaria '; end;
		   if salida = 5 then begin  estaciondesalida := estaciondesalida + ' El valle '; end;
		   if salida = 6 then begin  estaciondesalida := estaciondesalida + ' Meracdo '; end;
		   if salida = 7 then begin  estaciondesalida := estaciondesalida + ' Los simbolos '; end;
		   if salida = 8 then begin  estaciondesalida := estaciondesalida + ' Los Jardines '; end;
		   if salida = 9 then begin  estaciondesalida := estaciondesalida + ' La Rinconada '; end;
 end; 
 write('Seleccione sub estacion de DESTINO: '); readln(destino);
 		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Plaza Venezuela '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' La Bandera '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' Coche '; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' Ciudad universitaria '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' El valle '; end;
		   if destino = 6 then begin estaciondedestino := estaciondedestino + ' Meracdo '; end;
		   if destino = 7 then begin estaciondedestino := estaciondedestino + ' Los simbolos '; end;
		   if destino = 8 then begin estaciondedestino := estaciondedestino + ' Los Jardines '; end;
		   if destino = 9 then begin estaciondedestino := estaciondedestino +' La Rinconada '; end;
		   
while (destino <> 1) and (destino <> 2) and (destino <> 3)  and (destino <> 4)  
and (destino <> 5)  and (destino <> 6)  and (destino <> 7)  and (destino <> 8)  
and (destino <> 9) do
begin
write('Por favor elige una opcion en pantalla : '); 
readln(destino);
 		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Plaza Venezuela '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' La Bandera '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' Coche '; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' Ciudad universitaria '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' El valle '; end;
		   if destino = 6 then begin estaciondedestino := estaciondedestino + ' Meracdo '; end;
		   if destino = 7 then begin estaciondedestino := estaciondedestino + ' Los simbolos '; end;
		   if destino = 8 then begin estaciondedestino := estaciondedestino + ' Los Jardines '; end;
		   if destino = 9 then begin estaciondedestino := estaciondedestino +' La Rinconada '; end;
 end;  
		end;
end;
4: begin
 for repeticiones:= 1 to boletos do
begin
 if linea = 4 then lineaelegida := ' LINEA 4 ';
		writeln ('|============================= LINEA 4 ==============================|');
		writeln ('|====================================================================|');
		writeln ('|(1)-Zona Rental     (2)-Maternidad     (3)-Antimano                 |');
		writeln ('|(4)-Parque central  (5)-Artigas        (6)-Mamera                   |');
		writeln ('|(7)-Nuevo Circo     (8)-La Paz         (9)-Ruiz Pineda/ Las adjuntas|');
		writeln ('|(10)-Teatros        (11)-La yaragua    (12)-Zoologico               |');
		writeln ('|(13)-Capuchinos     (14)-Carapita                                   |');
		writeln ('|====================================================================|');
				   write('Seleccione sub estacion de SALIDA: '); readln(salida);
		   if salida = 1 then begin estaciondesalida := estaciondesalida + ' Zona Rental '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' Maternidad '; end;
		   if salida = 3 then begin estaciondesalida := estaciondesalida + ' Antimano '; end;
		   if salida = 4 then begin estaciondesalida := estaciondesalida + ' Parque central '; end;
		   if salida = 5 then begin estaciondesalida := estaciondesalida + ' Artigas'; end;
		   if salida = 6 then begin estaciondesalida := estaciondesalida + ' Mamera '; end;
		   if salida = 7 then begin estaciondesalida := estaciondesalida + ' Nuevo Circo '; end;
		   if salida = 8 then begin estaciondesalida := estaciondesalida + ' La Paz '; end;
		   if salida = 9 then begin estaciondesalida := estaciondesalida + ' Ruiz Pineda/ Las adjuntas '; end;
		   if salida = 10 then begin estaciondesalida := estaciondesalida + ' Teatros '; end;
		   if salida = 11 then begin estaciondesalida := estaciondesalida + ' La yaragua '; end;
		   if salida = 12 then begin estaciondesalida := estaciondesalida + ' Zoologico '; end;
		   if salida = 13 then begin estaciondesalida := estaciondesalida + ' Capuchinos '; end;
		   if salida = 14 then begin estaciondesalida := estaciondesalida + ' Carapita '; end;

while (salida <> 1) and (salida <> 2) and (salida <> 3)  and (salida <> 4)  
and (salida <> 5)  and (salida <> 6)  and (salida <> 7)  and (salida <> 8)  
and (salida <> 9)  and (salida <> 10)  and (salida <> 11)  and (salida <> 12)  
and (salida <> 13)  and (salida <> 14) do
begin
write('Por favor elige una opcion en pantalla : '); 
readln(salida);
		   if salida = 1 then begin estaciondesalida := estaciondesalida + ' Zona Rental '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' Maternidad '; end;
		   if salida = 3 then begin estaciondesalida := estaciondesalida + ' Antimano '; end;
		   if salida = 4 then begin estaciondesalida := estaciondesalida + ' Parque central '; end;
		   if salida = 5 then begin estaciondesalida := estaciondesalida + ' Artigas'; end;
		   if salida = 6 then begin estaciondesalida := estaciondesalida + ' Mamera '; end;
		   if salida = 7 then begin estaciondesalida := estaciondesalida + ' Nuevo Circo '; end;
		   if salida = 8 then begin estaciondesalida := estaciondesalida + ' La Paz '; end;
		   if salida = 9 then begin estaciondesalida := estaciondesalida + ' Ruiz Pineda/ Las adjuntas '; end;
		   if salida = 10 then begin estaciondesalida := estaciondesalida + ' Teatros '; end;
		   if salida = 11 then begin estaciondesalida := estaciondesalida + ' La yaragua '; end;
		   if salida = 12 then begin estaciondesalida := estaciondesalida + ' Zoologico '; end;
		   if salida = 13 then begin estaciondesalida := estaciondesalida + ' Capuchinos '; end;
		   if salida = 14 then begin estaciondesalida := estaciondesalida + ' Carapita '; end;
 end; 
 write('Seleccione sub estacion de DESTINO: '); readln(destino);
 		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Zona Rental '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' Maternidad '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' Antimano '; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' Parque central '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' Artigas '; end;
		   if destino = 6 then begin estaciondedestino := estaciondedestino + ' Mamera '; end;
		   if destino = 7 then begin estaciondedestino := estaciondedestino + ' Nuevo Circo '; end;
		   if destino = 8 then begin estaciondedestino := estaciondedestino + ' La Paz '; end;
		   if destino = 9 then begin estaciondedestino := estaciondedestino + ' Ruiz Pineda/ Las adjuntas '; end;
		   if destino = 10 then begin estaciondedestino := estaciondedestino + ' Teatros '; end;
		   if destino = 11 then begin estaciondedestino := estaciondedestino + ' La yaragua '; end;
		   if destino = 12 then begin estaciondedestino := estaciondedestino + ' Zoologico '; end;
		   if destino = 13 then begin estaciondedestino := estaciondedestino + ' Capuchinos '; end;
		   if destino = 14 then begin estaciondedestino := estaciondedestino + ' Carapita '; end;
		   
while (destino <> 1) and (destino <> 2) and (destino <> 3)  and (destino <> 4)  
and (destino <> 5)  and (destino <> 6)  and (destino <> 7)  and (destino <> 8)  
and (destino <> 9)  and (destino <> 10)  and (destino <> 11)  and (destino <> 12)  
and (destino <> 13)  and (destino <> 14) do
begin
write('Por favor elige una opcion en pantalla : '); 
readln(destino);
 		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Zona Rental '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' Maternidad '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' Antimano '; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' Parque central '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' Artigas '; end;
		   if destino = 6 then begin estaciondedestino := estaciondedestino + ' Mamera '; end;
		   if destino = 7 then begin estaciondedestino := estaciondedestino + ' Nuevo Circo '; end;
		   if destino = 8 then begin estaciondedestino := estaciondedestino + ' La Paz '; end;
		   if destino = 9 then begin estaciondedestino := estaciondedestino + ' Ruiz Pineda/ Las adjuntas '; end;
		   if destino = 10 then begin estaciondedestino := estaciondedestino + ' Teatros '; end;
		   if destino = 11 then begin estaciondedestino := estaciondedestino + ' La yaragua '; end;
		   if destino = 12 then begin estaciondedestino := estaciondedestino + ' Zoologico '; end;
		   if destino = 13 then begin estaciondedestino := estaciondedestino + ' Capuchinos '; end;
		   if destino = 14 then begin estaciondedestino := estaciondedestino + ' Carapita '; end;
 end;  
end;
end;
5 : begin 
 for repeticiones:= 1 to boletos do
begin
  if linea = 5 then lineaelegida := ' LINEA 5 ';
		writeln ('|=========================== LINEA 5 ==========================|');
		writeln ('|==============================================================|');
		writeln ('|(1)-Bello Monte           (2)-Bello Campo    (3)-Boleita      |');
		writeln ('|(4)-Las Mercedes          (5)-Hugo chavez    (6)-El marquez   |');
		writeln ('|(7)-Parque Simon bolivar  (8)-Montecristo    (9)-Warairarepero|');
		writeln ('|==============================================================|');
	    write('Seleccione sub estacion de SALIDA: '); readln(salida);
	       if salida = 1 then begin estaciondesalida := estaciondesalida + ' Bello Monte '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' Bello Campo '; end;
		   if salida = 3 then begin estaciondesalida := estaciondesalida + ' Boleita ';  end;
		   if salida = 4 then begin estaciondesalida := estaciondesalida + ' Las Mercedes '; end;
		   if salida = 5 then begin estaciondesalida := estaciondesalida + ' Hugo chavez '; end;
		   if salida = 6 then begin estaciondesalida := estaciondesalida + ' El marquez '; end;
		   if salida = 7 then begin estaciondesalida := estaciondesalida + ' Parque Simon bolivar '; end;
		   if salida = 8 then begin estaciondesalida := estaciondesalida + ' Montecristo '; end;
		   if salida = 9 then begin estaciondesalida := estaciondesalida + ' Warairarepero '; end;
				while (salida <> 1) and (salida <> 2) and (salida <> 3)  and (salida <> 4)  
				and (salida <> 5)  and (salida <> 6)  and (salida <> 7)  and (salida <> 8)  
				and (salida <> 9) do
begin
		write('Por favor elige una opcion en pantalla : '); 
		readln(salida);
		   if salida = 1 then begin estaciondesalida := estaciondesalida + ' Bello Monte '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' Bello Campo '; end;
		   if salida = 3 then begin estaciondesalida := estaciondesalida + ' Boleita ';  end;
		   if salida = 4 then begin estaciondesalida := estaciondesalida + ' Las Mercedes '; end;
		   if salida = 5 then begin estaciondesalida := estaciondesalida + ' Hugo chavez '; end;
		   if salida = 6 then begin estaciondesalida := estaciondesalida + ' El marquez '; end;
		   if salida = 7 then begin estaciondesalida := estaciondesalida + ' Parque Simon bolivar '; end;
		   if salida = 8 then begin estaciondesalida := estaciondesalida + ' Montecristo '; end;
		   if salida = 9 then begin estaciondesalida := estaciondesalida + ' Warairarepero '; end;
	end; 
		write('Seleccione sub estacion de DESTINO: '); readln(destino);
		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Bello Monte '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' Bello Campo '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' Boleita' ; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' Las Mercedes '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' Hugo chavez '; end;
		   if destino = 6 then begin estaciondedestino := estaciondedestino + ' El marquez '; end;
		   if destino = 7 then begin estaciondedestino := estaciondedestino + ' Parque Simon bolivar '; end;
		   if destino = 8 then begin estaciondedestino := estaciondedestino + ' Montecristo '; end;
		   if destino = 9 then begin estaciondedestino := estaciondedestino + ' Warairarepero '; end;
				while (destino <> 1) and (destino <> 2) and (destino <> 3)  and (destino <> 4)  
				and (destino <> 5)  and (destino <> 6)  and (destino <> 7)  and (destino <> 8)  
				and (destino <> 9) do
begin
		write('Por favor elige una opcion en pantalla : '); 
		readln(destino);
		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Bello Monte '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' Bello Campo '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' Boleita' ; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' Las Mercedes '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' Hugo chavez '; end;
		   if destino = 6 then begin estaciondedestino := estaciondedestino + ' El marquez '; end;
		   if destino = 7 then begin estaciondedestino := estaciondedestino + ' Parque Simon bolivar '; end;
		   if destino = 8 then begin estaciondedestino := estaciondedestino + ' Montecristo '; end;
		   if destino = 9 then begin estaciondedestino := estaciondedestino + ' Warairarepero '; end;
 end;  
		end;
end;
6 : begin
for repeticiones:= 1 to boletos do
begin
 if linea = 6 then lineaelegida := ' LINEA 6 ';
		writeln ('|=============== LINEA 6 ===============|');
		writeln ('|=======================================|');
		writeln ('|(1)-Zoologico          (2)-La Rinconada|');
		writeln ('|=======================================|');
		write('Seleccione sub estacion de SALIDA: '); readln(salida);
		   if salida = 1 then begin estaciondesalida := estaciondesalida + ' Zoologico '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' La Rinconada '; end;
				while (salida <> 1) and (salida <> 2) do
begin
		write('Por favor elige una opcion en pantalla : '); 
		readln(salida);
		   if salida = 1 then begin estaciondesalida := estaciondesalida + ' Zoologico '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' La Rinconada '; end;
 end; 
		write('Seleccione sub estacion de DESTINO: '); readln(destino);
		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Zoologico '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' La Rinconada '; end;
				while (destino <> 1) and (destino <> 2) do
begin
		write('Por favor elige una opcion en pantalla : '); 
		readln(destino);
		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Zoologico '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' La Rinconada '; end;
 end;  
		end;
end;
7 : begin
for repeticiones:= 1 to boletos do
begin
 if linea = 7 then lineaelegida := ' LINEA 7 ';
		writeln ('|======================== LINEA 7 ==========================|');
		writeln ('|===========================================================|');
		writeln ('|(1)-Las Flores    (2)-El Cristo            (3)-Roosvelt    |');
		writeln ('|(4)-Panteon       (5)-Roca Tarpeya         (6)-La bandera  |');
		writeln ('|(7)-Socorro       (8)-Presidente medina    (9)-Los ilustres|');
		writeln ('|(10)-La Hoyada    (11)-INCES                               |');
		writeln ('|===========================================================|');
		write('Seleccione sub estacion de SALIDA: '); readln(salida);
		   if salida = 1 then begin estaciondesalida := estaciondesalida + ' Las Flores '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' El Cristo '; end;
		   if salida = 3 then begin estaciondesalida := estaciondesalida + ' Roosvelt '; end;
		   if salida = 4 then begin estaciondesalida := estaciondesalida + ' Panteon '; end;
		   if salida = 5 then begin estaciondesalida := estaciondesalida + ' Roca Tarpeya '; end;
		   if salida = 6 then begin estaciondesalida := estaciondesalida + ' La bandera '; end;
		   if salida = 7 then begin estaciondesalida := estaciondesalida + ' Socorro '; end;
		   if salida = 8 then begin estaciondesalida := estaciondesalida + ' Presidente medina '; end;
		   if salida = 9 then begin estaciondesalida := estaciondesalida + ' Los ilustres '; end;
		   if salida = 10 then begin estaciondesalida := estaciondesalida + ' La Hoyada '; end;
		   if salida = 11 then begin estaciondesalida := estaciondesalida + ' INCES '; end;
				while (salida <> 1) and (salida <> 2) and (salida <> 3)  and (salida <> 4)  
				and (salida <> 5)  and (salida <> 6)  and (salida <> 7)  and (salida <> 8)  
				and (salida <> 9)  and (salida <> 10)  and (salida <> 11) do
begin
		   write('Por favor elige una opcion en pantalla : '); 
		   readln(salida);
		   if salida = 1 then begin estaciondesalida := estaciondesalida + ' Las Flores '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' El Cristo '; end;
		   if salida = 3 then begin estaciondesalida := estaciondesalida + ' Roosvelt '; end;
		   if salida = 4 then begin estaciondesalida := estaciondesalida + ' Panteon '; end;
		   if salida = 5 then begin estaciondesalida := estaciondesalida + ' Roca Tarpeya '; end;
		   if salida = 6 then begin estaciondesalida := estaciondesalida + ' La bandera '; end;
		   if salida = 7 then begin estaciondesalida := estaciondesalida + ' Socorro '; end;
		   if salida = 8 then begin estaciondesalida := estaciondesalida + ' Presidente medina '; end;
		   if salida = 9 then begin estaciondesalida := estaciondesalida + ' Los ilustres '; end;
		   if salida = 10 then begin estaciondesalida := estaciondesalida + ' La Hoyada '; end;
		   if salida = 11 then begin estaciondesalida := estaciondesalida + ' INCES '; end;
			end; 
		   write('Seleccione sub estacion de DESTINO: '); readln(destino);
		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Las Flores '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' El Cristo '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' Roosvelt '; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' Panteon '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' Roca Tarpeya '; end;
		   if destino = 6 then begin estaciondedestino := estaciondedestino + ' La bandera '; end;
		   if destino = 7 then begin estaciondedestino := estaciondedestino + ' Socorro '; end;
		   if destino = 8 then begin estaciondedestino := estaciondedestino + ' Presidente medina '; end;
		   if destino = 9 then begin estaciondedestino := estaciondedestino + ' Los ilustres '; end;
		   if destino = 10 then begin estaciondedestino := estaciondedestino + ' La Hoyada '; end;
		   if destino = 11 then begin estaciondedestino := estaciondedestino + ' INCES '; end;
				while (destino <> 1) and (destino <> 2) and (destino <> 3)  and (destino <> 4)  
				and (destino <> 5)  and (destino <> 6)  and (destino <> 7)  and (destino <> 8)  
				and (destino <> 9)  and (destino <> 10)  and (destino <> 11) do
begin
           write('Por favor elige una opcion en pantalla : '); 
	       readln(destino);
	       		   if destino = 1 then estaciondedestino := 'Las Flores';
		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Las Flores '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' El Cristo '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' Roosvelt '; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' Panteon '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' Roca Tarpeya '; end;
		   if destino = 6 then begin estaciondedestino := estaciondedestino + ' La bandera '; end;
		   if destino = 7 then begin estaciondedestino := estaciondedestino + ' Socorro '; end;
		   if destino = 8 then begin estaciondedestino := estaciondedestino + ' Presidente medina '; end;
		   if destino = 9 then begin estaciondedestino := estaciondedestino + ' Los ilustres '; end;
		   if destino = 10 then begin estaciondedestino := estaciondedestino + ' La Hoyada '; end;
		   if destino = 11 then begin estaciondedestino := estaciondedestino + ' INCES '; end;
		   end;  

		end;
end;
8 : begin 
for repeticiones:= 1 to boletos do
begin
 if linea = 8 then lineaelegida := ' LINEA 8 ';
		writeln ('|======================== CLABETREN =========================|');
		writeln ('|============================================================|');
		writeln ('|(1)-Petare 2      (2)-5 de Julio           (3)-warairarepano|');
		writeln ('|(4)-19 de abril   (5)-24 de Julio                           |');
		writeln ('|============================================================|');
		write('Seleccione sub estacion de SALIDA: '); readln(salida);
		   if salida = 1 then begin estaciondesalida := estaciondesalida + ' Petare 2 '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' 5 de Julio '; end;
		   if salida = 3 then begin estaciondesalida := estaciondesalida + ' warairarepano '; end;
		   if salida = 4 then begin estaciondesalida := estaciondesalida + ' 19 de abril '; end;
		   if salida = 5 then begin estaciondesalida := estaciondesalida + ' 24 de Julio '; end;
				while (salida <> 1) and (salida <> 2) and (salida <> 3)  and (salida <> 4)  
				and (salida <> 5) do
begin
		   write('Por favor elige una opcion en pantalla : '); 
		   readln(salida);
		   if salida = 1 then begin estaciondesalida := estaciondesalida + ' Petare 2 '; end;
		   if salida = 2 then begin estaciondesalida := estaciondesalida + ' 5 de Julio '; end;
		   if salida = 3 then begin estaciondesalida := estaciondesalida + ' warairarepano '; end;
		   if salida = 4 then begin estaciondesalida := estaciondesalida + ' 19 de abril '; end;
		   if salida = 5 then begin estaciondesalida := estaciondesalida + ' 24 de Julio '; end;
			end; 
		   write('Seleccione sub estacion de DESTINO: '); readln(destino);
		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Petare 2 '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' 5 de Julio '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' warairarepano '; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' 19 de abril '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' 24 de Julio '; end;
				while (destino <> 1) and (destino <> 2) and (destino <> 3)  and (destino <> 4)  
				and (destino <> 5) do
begin
           write('Por favor elige una opcion en pantalla : '); 
	       readln(destino);
		   if destino = 1 then begin estaciondedestino := estaciondedestino + ' Petare 2 '; end;
		   if destino = 2 then begin estaciondedestino := estaciondedestino + ' 5 de Julio '; end;
		   if destino = 3 then begin estaciondedestino := estaciondedestino + ' warairarepano '; end;
		   if destino = 4 then begin estaciondedestino := estaciondedestino + ' 19 de abril '; end;
		   if destino = 5 then begin estaciondedestino := estaciondedestino + ' 24 de Julio '; end;
		   end;  
 
	end;
end; 
end;
				writeln;
				writeln('|==================Factura==================|');
				writeln('Nombre: ', nombre_apellido);
				writeln('Cedula: ', cedula);
				writeln('Metodo de transporte: ',transporte);
				writeln('Estacion de salida: ',estaciondesalida);
				writeln('Estacion de destino: ',estaciondedestino);
				writeln('Linea elegida: ', lineaelegida);
				writeln('Monto a pagar: ',montoapagar,'$');
				writeln('|===========================================|');
				writeln;
				writeln('|===========================================|');
				writeln('| Esta usted seguro de realizar su compra?  |');
				writeln('|Presione (1) para continuar...             |');
				writeln('|Presione (2) para salir...                 |');
				writeln('|===========================================|');
				  write('---> '); readln(verificarcompra);
  while (verificarcompra <> 1) and (verificarcompra <> 2) do
begin
	write('Por favor elige una opcion en pantalla : '); 
		readln(verificarcompra);
 end;
clrscr;
case verificarcompra of
				1: begin 
				writeln('|==================Factura==================|');
				writeln('Nombre: ', nombre_apellido);
				writeln('Cedula: ', cedula);
				writeln('Metodo de transporte: ',transporte);
				writeln('Estacion de salida: ',estaciondesalida);
				writeln('Estacion de destino: ',estaciondedestino);
				writeln('Linea elegida: ', lineaelegida);
				writeln('Monto a pagar: ',montoapagar,'$');
				writeln('|===========================================|');
				write('Ingrese el dinero: '); readln(pago);
				writeln('|===========================================|');
				writeln;

		if pago > montoapagar then begin
		vuelto := montoapagar-pago;
		writeln('Estas dando dinero de mas, se te devolveran ', -1*vuelto,'$');
		writeln('|===========================================|');
		end;

			if pago < montoapagar then  begin
			repeat
			if pago < montoapagar then writeln('Te falta dinero, exactamente ',pago-montoapagar,'$', ' Recuerda que debes pagar exactamente: ',montoapagar,'$');
			write('Ingrese el dinero aqui: '); readln(pago);
			writeln('|===========================================|');
			until pago >= montoapagar;
			if pago > montoapagar  then begin
			vuelto := montoapagar-pago;
			writeln('Estas dando dinero de mas, se te devolveran ', -1*vuelto,'$');
			end;
			end;

				writeln;
				writeln('|==================Factura==================|');
				writeln('Nombre: ', nombre_apellido);              
				writeln('Cedula: ', cedula);
				writeln('Metodo de transporte: ',transporte);
				writeln('Estacion de salida: ',estaciondesalida);
				writeln('Estacion de destino: ',estaciondedestino);
				writeln('Linea elegida: ', lineaelegida);
				writeln('Costo : ',montoapagar,'$');
				writeln('|===========================================|');

		writeln;
		writeln('===========================');
		writeln('Para avanzar presione enter');
		writeln('===========================');
			readln;
		clrscr;

		Writeln('|==================================================|');
		writeln('|                |Bienvenido a menu|               |');
		Writeln('|==================================================|');
		writeln('| Presione (1) Para utilizar su boleto.            |');
		writeln('| Presione (2) Para Ver sistema.                   |');
		writeln('| Presione (3) Para salir del sistema.             |');
		Writeln('|==================================================|');
		  write('|---> '); readln(menu);
  
while (menu <> 1) and (menu <> 2) and (menu <> 3) do
begin
	write('Por favor elige una opcion en pantalla : '); 
		readln(menu);
 end;

case menu of 

					1: begin   writeln('===================================');
							   writeln('Estas seguro de que quieres usarlo?');
							   writeln('Presione (1) Si quiere usarlo      ');
							   writeln('Presione (2) Si no quiere usarlo   ');
							   writeln('===================================');
								 write('---> '); readln(menu2);
								 while (menu2 <> 1) and (menu2 <> 2)  do
begin
	write('Por favor elige una opcion en pantalla : '); 
		readln(menu2);
 end;

case menu2 of

					1: begin   
					writeln;
					writeln('==========================================');
					writeln('Para continuar por favor ingrese su cedula');
					writeln('==========================================');
					  write('---> '); repeat readln(cedula2);
  
  
  if cedula2 <> cedula then write(' Cedula incorrecta, Por favor intentelo de nuevo: ');
  until cedula2 = cedula;
						writeln;
						writeln('==========================================');
						writeln('Has utilizado 1 boleto');
						writeln('Metodo de transporte: ',transporte);
						writeln('Estacion de salida: ',estaciondesalida);
						writeln('Estacion de destino: ',estaciondedestino);
						writeln('Linea elegida: ', lineaelegida);
						writeln('Boletos Comprados: ', boletos);
						writeln('Boletos restantes: ', boletos-boletos);
						writeln('Costo : ', montoapagar,'$');
							if boletos-1 = 0 then writeln('Si deseas comprar otro boleto, reinicia el sitema');
				 writeln('==========================================');
				 writeln;
				 Writeln('|=========================================================|');
				 writeln('|Que tenga un feliz viaje y gracias por usar metro caracas|');
				 Writeln('|=========================================================|');
				end;
  
					2: begin 
						Writeln('|==================================================|');
						Writeln('|      Espero que tenga feliz dia, hasta luego     |');
						Writeln('|==================================================|');
						end;
end;

end;

					2: begin 
					writeln('===================================');
					writeln('      Apartado de ver sistema      ');
					writeln('===================================');
					writeln('         Ingrese la clave          ');
					writeln('===================================');
					  write('---> '); repeat readln(clave);
					  if clave <> 1234 then write('Clave incorrecta, por favor intentelo de nuevo: ');
					  until clave = 1234;
  
  
  
								writeln;
								writeln('===================================');
								writeln('         Datos del usuario         ');
								writeln('===================================');
								writeln('Nombre : ', nombre_apellido);
								writeln('Cedula : ', cedula);
								writeln('Boletos Comprados: ', boletos);
								writeln('Boletos restantes: ', boletos-boletos);
								writeln('Linea elegida: ', lineaelegida);
								writeln('Costo total: ', montoapagar,'$');
								writeln('===================================');
								writeln('ingresados por linea: 1');
								writeln('Promedio de venta: ', montoapagar div boletos,'$');
								writeln('===================================');
								writeln;
								 Writeln('|=========================================================|');
								 writeln('|Que tenga un feliz viaje y gracias por usar metro caracas|');
								 Writeln('|=========================================================|');
								end;  

						3: begin 
							Writeln('|==================================================|');
							Writeln('|      Espero que tenga feliz dia, hasta luego     |');
							Writeln('|==================================================|');
							end;

					end;

			end;

2: begin 
    Writeln('|==================================================|');
	Writeln('|      Espero que tenga feliz dia, hasta luego     |');
	Writeln('|==================================================|');
	end;
	
end;	
end;

						2: begin
	
							Writeln('|      Espero que tenga feliz dia, hasta luego     |');
							Writeln('|==================================================|');
	
						end;
				end;
		end.
