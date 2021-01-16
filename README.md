# Evaluación Primer Bimestre<br/>
Desarrollo de un chat<br/>
Freddy Valverde<br/>
<h2>Herramientas: Firebase, Ionic, Angular</h2><br/>
Creación del proyecto de Firebase<br/>
Primero acceder a console.firebase.google<br/>
crear un proyecto, y activar la autenticación por correo y contraseña. Además, de crear una base de datos Firestore<br/>
<h2>Inicio y creacion de un proyecto ionic</h2><br/>
Cree un proyecto de ionic, con angular, ademas se instalaron los plugins de @angular/fire y firebase en nuestro proyecto. Tambien se instalo crypto-js para la encriptación del mensaje<br/>
<h2>Desarrollo</h2><br/>
Primero en se agregaron la paginas de login y chat dentro del directorio app se encontraran las carpetas de cada página. Ademas de un servicio que se encuentra en la carpeta services de app la cual nos ayudará a conectarnos con firebase.<br/>
 <h2>environment.ts</h2><br/>
 Aqui nosotros vamos a copiar la variable con las claves de acceso a firebase.<br/>
 <h2>app.module.ts>/h2><br/>
  Aqui importe las librerias necesarias para la autenticación, store de firebase, el environment con la clave y el modulo de firebase.<br/>
  <h2>app-routing.module.ts</h2><br/>
  Aqui indico que la pagina inicial es el login siempre y cuando no este registrado o iniciado sesión, en caso contrario lo dirija al chat directamente.<br/>
  <h2>chat.service.ts>/h2><br/>
    Aqui en primera instancia se declaran dos interfaces la cual una es para los datos del usuario y otra para los datos del mensaje. En el usuario manejamos el uid y el email. En el mensaje manejamos un id, id de quien envio el mensaje, el contenido del mensaje, la fecha de creación del mensaje y un validador para saber si es mi mensaje o no.<br/>
    <h3>Funciones</h3><br/>
    La primera funcion que se encuetra es onAuthStatechanged esta controlara si el usuario a iniciado sesión o no. Para en tal caso enviarlo a la pagina del login o del chat.<br/>
    La función addChatMessage como su nombre lo inidca permite agregar un nuevo mensaje a la colección de mensajes.<br/>
    La función getChatMessages Obtiene un observable de mensajes que se actualiza cada vez que se agrega un mensaje nuevo. Donde mapea cada uno de los mensajes de la colección y toma el nombre del usuario esto en base a la función getUsers, indica si el mensaje leido es mio o no y finalmente desencripta el mensaje de objeto<br/>
    La función getUsers pemite obtener todos los usuarios para que podamos resolver los nombres de los usuarios.<br/>
    La funcion getUserForMsg ayuda a encontrar el nombre real (correo electrónico) de un usuario en función de un UID y la matriz de usuarios.<br/>
    La función encryptMsg permite encritar un mensaje con cryptoJS mientras que la función decrypt realiza la función de desencriptar.<br/>
  <h2>login.module.ts>h2><br/>
    Aqui importamos el formsModule de @angular/forms para poder crear el formulario de registro.<br/>
    <h2>login.page.ts</h2><br/>
    <h3>Funciones</h3><br/>
    con una función async realizaremos el registro e inicio de sesión de usuarios. Basicamente aqui controlaremos un poco lo que ingrese el usuario a la pagina antes de registrarse o iniciar sesión. Controlamos el enrutamiento, en el caso de que ingrese datos erroroneos, entre otros.<br/>
    <h2>login.page.html</h2><br/>
    Aqui en primera instancia se hizo uso del formGroup para la creación del formulario. Los dos inputs tienen su ngIf que evaluara si los datos ingresados son correcto y en el caso que no muestre el error. Además cuenta con los botones para el registro e inicio de sesión.<br/>
    <h2>chat.page.ts</h2><br/>
    <h3>Funciones</h3><br/>
    La función ngOnit llama a la función getChatMessages es decir obtendremos la colección de mensajes que se mostrará.<br/>
    La función sendMessage manda el mensaje a addChatMessage del servicio y despues procede a limpiar el campo.<br/>
    La función signOut basicamente lo que hace es cerrar sesión.<br/>
    <h2>cht.page.html</h2><br/>
    <h3>Funciones</h3><br/>
    En el header tenemos el boton para cerrar sesión.<br/>
    En el footer tenemos el input para escribir un mensaje<br/>
    Y en el content basicamente comienza con el*ngFor escanear cada mensaje de la colección. Despues analiza si el mensaje es mio lo poner de la mitad para la derecha, si no lo ubica desde el inicio. con ngClass basicamente nos sirve para identificarlos con el estilo css del tipo de mensaje que sea.Despues muestra el nombre de quien es el mensaje, el contenido del mensaje. La fecha de creción del mensaje.<br/>
    <h2>chat.page.css y login.page.css</h2><br/>
    Aqui solo controlamos los estilos de las paginas y cada uno de sus componentes.<br/>
    <h1>APK</h1><br/>
    Al apk fue generada con cordova la cual se encuentra en la carpeta apk de este repositorio.
    <h1>Video del funcionamiento</h1><br/>
    El siguiente enlace es del video explicativo de como funciona la aplicación en si.<br/>
    https://youtu.be/lj3mMCxuAqE
    
    
    
 
  
