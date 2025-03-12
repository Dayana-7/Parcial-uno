saldo = 7000
intentos_fallidos = 0
usuario_correcto = "Dayana Jovel"
pin_correcto = "9078"

def mostrar_menu():
    print("Cajero automático")
    print("1. Consultar saldo")
    print("2. Retirar dinero")
    print("3. Depositar")
    print("4. Salir del cajero")

def iniciar_sesion():
    global intentos_fallidos
    while intentos_fallidos < 3:
        usuario = input("ingrese su usuario")
        pin_input = input("ingrese pin:")
        if usuario == usuario_correcto and pin_input == pin_correcto:
            print("inicio de sesion exitoso")
            return True
        else:
            print("usuario o pin incorrecto.")
            intentos_fallidos +=1
            return False
        if not iniciar_sesion():
            print("No se puede iniciar sesion.")
            exit()

            while True:
                mostrar_menu()
    try:
        opcion = int(input("Seleccione una opción: "))
        if opcion == 1:
            print(f"Su saldo actual es: ${saldo}")
        elif opcion == 2:
            monto = float(input("Ingrese el monto a retirar: "))
            if monto <= 0:
                print("El monto no debe ser cero.")
            elif monto > saldo:
                print("Saldos insuficientes.")
            else:
                saldo -= monto
                print(f"Retiro exitoso. Su nuevo saldo es: ${saldo}")

        elif opcion == 3:
            monto = float(input("Ingrese el monto a depositar: "))
            if monto <= 0:
                print("El monto no debe ser cero.")
            else:
                saldo += monto
                print(f"Depósito exitoso. Su nuevo saldo es: ${saldo}")

        elif opcion == 4:
            ("salir del cajero")
            
            print("¡Gracias por usar nuestro cajero automático!")
            exit()
        else:
            print("Opción no válida. Intente de nuevo.")
    except ValueError:
        print("Error: Ingrese un número que sea válido.")
