sept 16, 2026

## **Nueva revisión historias de usuario \- REMOTOR \- Diana Rosero y Julio Ruiz \- Transcripción**

### **00:00:00**

&nbsp;

**Julián Perdomo:** Listo. Acá tenemos pues una de las historias de usuario, en este caso es la creación de la recepción.

**DIANA:** Mm.

**Julián Perdomo:** Bueno, acá tenemos pues la situación actual y acá viene lo aquí

**DIANA:** Correcto.

**Julián Perdomo:** se viene uno de los primeros cambios que hicimos. Nosotros anteriormente pues estábamos manejando, no sé si te acuerdas, lo de H1, H2, H3.

**DIANA:** Sí, perfecto. nombre de cada historia de usuario.

**Julián Perdomo:** Sí, señora. Pues en este caso en otros esa parte la suprimimos y colocamos es lo siguiente, pues se desea el el proceso de creación función, bueno, la descripción completa, una descripción detallada de la situación y acabamos con el tema. En este caso,

**DIANA:** Okay.

**Julián Perdomo:** pues la consulta y el autoguardado, pues al ingresar la placa o la sigla del vehículo, el sistema debe permitir de manera ágil autocompletar la entidad, marca, eh clase, color. Es esos campos se configuran como solo lectura para el usuario. Eso fue una de las partes que nos pediste en aquel

**DIANA:** Sí,

**Julián Perdomo:** momento.

**DIANA:** que sí que fueran más explícitos.

**Julián Perdomo:** En este caso tenemos unos campos de filtrado de búsqueda.

&nbsp;

&nbsp;

### **00:01:25**

&nbsp;

**Julián Perdomo:** En este caso, pues puede ser o por sigla o por o por placa. Es tipo en tipo test un input.

**DIANA:** Mm.

**Julián Perdomo:** Tenemos también el filtrado, pues por la entidad o por contrato,

**DIANA:** Pero todas las como ahora sí.

**Julián Perdomo:** caso eh pues Ajá.

**DIANA:** Ah, serán listas desplegables. Correcto.

**Julián Perdomo:** Eh, acá tenemos en campos de visualización tenemos eh la entidad como campo desplegable, tenemos la marca, eh eso como los campitos, lo que lo que se va a visualizar, ¿vale? Eh,

**DIANA:** Listo. Para un segundo, por favor. Cuando decimos campos de filtrado, entidad, ¿cómo van a ser? Por ejemplo, en este momento, si ustedes ingresan placa, es para que ustedes vayan pensando dentro del flujo y por ende cómo irían quedando los

**Julián Perdomo:** sí,

**DIANA:** prototipos.

**Julián Perdomo:** sí,

**DIANA:** Si tú me dices el primero placa, entonces yo pongo AC 1 2 3\.

**Julián Perdomo:** sí.

**DIANA:** El apenas yo le dé enter, él va a ir a la base de datos por debajo, me trae los datos y ya sabemos que el resto de datos que dijimos, qué color, qué marca, qué modelo, no sé qué, se ponen automáticamente.

&nbsp;

&nbsp;

### **00:02:46**

&nbsp;

**Julián Perdomo:** Sí.

**DIANA:** asumamos que es el camino feliz, que es el de siesta y y qué y pone todos esos datos. Lo mismo pasa consig, ¿no es cierto?

**Julián Perdomo:** Sí,

**DIANA:** Listo. Perfecto. Ahora, si tú me dices que yo voy a buscar por entidad, viene la primera pregunta.

**Julián Perdomo:** sí,

**DIANA:** Busco, ejemplo, pongo solo, solo pongo policía y él me va a traer la lista en

**Julián Perdomo:** sí.

**DIANA:** algún campo, me supongo yo, una lista de 5 a 10,000 o lo todos los vehículos que tenga de qué?

**Julián Perdomo:** Es sí

**DIANA:** Sí,

**Julián Perdomo:** teoría.

**DIANA:** que se va, ¿no? O sea, es esas son las cosas que tienen que definir, chicos, tanto en las historias de usuario como en los prototipos.

**Julián Perdomo:** Sí.

**DIANA:** Y por eso les digo que se vayan focalizando hacia los prototipos. ¿Por qué? Porque ustedes me dicen, por ejemplo, eh, la placa la tenemos clara. usted busca por el la placa y como cosas,

**Julián Perdomo:** Sì.

**DIANA:** o sea, ah, busqué por la placa y no es necesario, o sea, que yo puedo hacerla exclusivamente por la placa, o sea, que si pongo la placa no es necesario que ponga la sigla porque no todos los carros tienen sigla.

&nbsp;

&nbsp;

### **00:04:12**

&nbsp;

**DIANA:** Entonces,

**Julián Perdomo:** Sí.

**DIANA:** busco la placa AC 1 2 3 y apenas yo le di un da enter o el botón buscar. Eso es lo que tienen que ir pensando. Por los prototipos para mí, para mí frente a usabilidad y experiencias de usuario es escribe, digita la placa, le da enter y de manera eh asíncrona él va y busca de una vez esa placa. si la encuentra, ustedes ya definen dentro del prototipo y dentro de la historia de usuario de ah, se muestra primero un mensaje que dice vehículo encontrado y luego le tengo que dar cerrar a esa a ese popup, eh, y me muestran los datos o busqué la placa y de una trajo los datos sin tener que mostrar mostrar mensaje. Por eso le digo, digo que vayan pensando de una vez en los prototipos. ¿Listo? Ah, ya lo buscó. Ahora, ¿cuál es la vaina? Si ustedes me dicen,"Vamos a buscar por entidad." La entidad a mí me da cuando hacemos los contratos, la entidad a mí me dice,"Tengo, pongámoslo, 10 vehículos, ¿no es cierto? Y si usted me dice, ay, yo vengo, ah, está el filtro." Y entonces como esta es yo la puedo escribir ahí, no me están diciendo si la voy a digitar o si va a ser una lista desplegable.

&nbsp;

&nbsp;

### **00:05:47**

&nbsp;

**DIANA:** Entonces asumamos que me están diciendo que la voy a escribir. Entonces yo escribo en eh policía. Cuando yo le policía, volvemos a la misma acción. un da enter o cuando le dé el botón buscar. Ah, bueno, asumamos que dijimos que enter tamb botón enter eh enter y él me va a traer una lista larguísima de todos los

**Julián Perdomo:** Sí.

**DIANA:** vehículos que tiene esa entidad y por ende lista yo asumo que voy a poder seleccionar alguno de ellos y que me traiga toda esa información. Entonces ahí es donde tienen que pensar yo, por lo menos yo, eso sería algo que hay que decirle a ellos. Eh, hay que preguntar si quieren búsqueda por entidad y por el contrato, porque el contrato va a ser lo mismo. El tengan en cuenta que el contrato eh, acuérdense de base de datos,

**Julián Perdomo:** Sí.

**DIANA:** eh una entidad tiene un contrato con el taller González, ¿no es cierto? De esa sola entidad.

**Julián Perdomo:** H

**DIANA:** una esa es una teraria, o sea, tenemos entidad o entre ellas, perdón, no, no es necesaria teraria, ahora que lo pienso, tenemos una taller González, tenemos una entidad, la relación que la une a ellas es que tienen un contrato, ¿no es cierto? Y pueden tener de uno a muchos y de muchos a muchos.

&nbsp;

&nbsp;

### **00:07:18**

&nbsp;

**DIANA:** Es decir, la taller González puede tener de uno a muchos contratos con una entidad o con muchas entidades. Y lo mismo, esa entidad puede tener un contrato o muchos contratos con con González. Entonces, ¿se acuerdan que ahí cuando eran de muchos a muchos se genera una tabla adicional que

**Julián Perdomo:** Sí.

**DIANA:** tiene las llaves primarias de ambas? Y si se nos hace necesaria puede tener más atributos. ¿Ya? Entonces, por ejemplo, si ustedes me dicen por entidad, les voy a poner porque está pasando policía, policía hoy tiene, digamos, 10 carros y les pasa que la policía de Bogotá,

**Julián Perdomo:** Sí.

**DIANA:** la de Medellín, la alcaldía, le regalan carros. Entonces ahora yo vuelvo a buscar ahora por entidad, ya no van a ser 10, sino 20 carros. ¿Listo?

**Julián Perdomo:** Ah.

**DIANA:** Entonces, tengan en cuenta que cada vez que yo voy a buscar por entidad, ya puede empezar a superar, eh, o sea, van a tener demasiados carros como para yo ponerme en una lista desplegable a buscar esto. ¿Por qué se los digo? A menos de que aquí se les pida estrictamente, o sea, nosotros como taller González les digamos, necesitamos, y no sé si eso se los dijeron eh don Edwin y don Luis Miguel, se los dijeron, necesitamos que sí y solo sí.

&nbsp;

&nbsp;

### **00:08:48**

&nbsp;

**DIANA:** o tenga la búsqueda por entidad. Yo no lo veo, no lo veo como tan viable.

**Julián Perdomo's Presentation:** M.

**Julián Perdomo:** M.

**DIANA:** Ya puede ser más vale una en común, es decir, busco entidad y a su vez busco la placa como para hacer una búsqueda más rápida, más eficiente, porque yo ya sé de, ay, venga, esto es policía y entonces la puedo buscar por policía y por la placa o por la sigla o eh ya lo mismo el contrato,

**Julián Perdomo:** Sí.

**DIANA:** que era lo que les explicaba, son de muchos a muchos. Y ustedes me muestran el contrato en una lista desplegable. Honestamente, por ejemplo, uno, yo no me acordar el número del contrato y el nombre del contrato y policía 1 2026\. Además uno dice,"Ah, no, es que es el del año." Entonces aparecería 2026 gu policía contrato uno.

**Julián Perdomo:** Mhm.

**DIANA:** Pero los contratos se pueden haber muchos en el mismo año. Yo pude haber contratado en el del primero de enero a digamos al a 28 de febrero un solo contrato y cada dos meses tengo un contrato. Entonces voy a tener una lista solo en policía, mínimo de unos seis estamos hablando. Y si pasa lo mismo con las otras entidades, o sea, la lista va a ser larga.

&nbsp;

&nbsp;

### **00:10:17**

&nbsp;

**DIANA:** ¿Listo?

**Julián Perdomo:** Marquista.

**DIANA:** ¿A qué voy con eso?

**Julián Perdomo:** Listo.

**DIANA:** Que para mí, para mí eso sería algo que, por ejemplo, ustedes lo pueden dejar porque esto va a estar sujeto. Puede que ahorita no lo cambiemos, pero sí lo vamos a cambiar de pronto a la hora de ya empezar la ejecución. Ah, venga. ¿Ustedes de pronto quieren que también se haga la búsqueda por entidad, por contrato, no? ¿Qué es lo que más ustedes tienen que hacer? Es nosotros el software que lo vamos a hacer se lo proponemos de que sea estrictamente por placa o por sigla, porque no todos los vehículos tienen siglas. Entonces, es esa sugerencia porque no yo no lo veo tan viable por esas por esas búsquedas.

**Julián Perdomo:** Alo.

**DIANA:** La identidad la veo parcialmente viable.

**Julián Perdomo:** Ah.

**DIANA:** Sí, mientras yo también le ponga placa para que cuando hagan la consulta a la base de datos, o sea, el SQL con todos sus join y todos esos pueda ser más efectivo de,"Ah, venga, es que yo ya también voy a ir a buscar de una vez la entidad y ahí ya sé cuál va a ser, pero antes no." Sí. Además,

**Julián Perdomo:** Aha.

**DIANA:** tienen que tener en cuenta algo ya pensando en bases de datos y eso.

&nbsp;

&nbsp;

### **00:11:27**

&nbsp;

**DIANA:** El contrato puede ser el contrato uno y en el contrato dos están los mismos vehículos. Entonces, ¿de qué me sirve buscar contrato uno o contrato dos si voy a tener los mismos vehículos que tuve en el contrato uno, que tuve en el contrato dos? Puedo tener de pronto más o en algunos casos puedo tener menos porque hay veces les dan de baja. Entonces, por eso no las veo como tan viable. No sé si me hice entender.

**Julián Perdomo:** Sí, sí, sí. Ahí estamos. Claros.

**DIANA:** Listo. Listo. Entonces esa.

**Julián Perdomo:** Listo.

**DIANA:** Bueno, sigamos.

**Julián Perdomo:** Entonces esta parte la vamos a corregir nosotros, ¿vale?

**DIANA:** Sí, o sea, no, pero si ustedes, o sea, a qué le digo? O sea, yo no lo yo desde acá no lo veo viable,

**Julián Perdomo:** Sí,

**DIANA:** pero si ustedes como desarrolladores dicen,"No, sí es completamente viable, lo pueden lo pueden hacer, pero no lo veo como tan

**Julián Perdomo:** ¿no? Sí, pensándolo bien, sí, pues en ese caso si tien razón, es más viable buscarlo por la placa o por la sigla. evitar tanto porque pues si uno se lesiona la entidad o el contrato, pues no,

&nbsp;

&nbsp;

### **00:12:34**

&nbsp;

**DIANA:** Sí, o sea,

**Julián Perdomo:** o sea, eso no no valdría la pena, ¿no?

**DIANA:** Sí. O sea, esos datos entran dentro de lo que se va visualizar que tiene. Ah, esta vez el vehículo entró por policía, o sea, esa es su entidad, ¿ya?

**Julián Perdomo:** Sí.

**DIANA:** Ah, policía. Y este en este momento y tengan en cuenta que los contratos lo pueden manejar también así que me acabo de dar cuenta, los contratos algunos estarán activos y otros estarán pues ya pasaron, o sea, ya terminaron. Entonces eh ustedes dirán,"No, solo mostramos los contratos activos." Entonces, no porque por ejemplo a mí me puede llegar una garantía, que es algo de lo que les iba a hablar, que no lo vi por ninguna parte y el software lo tiene que manejar. Venga, a mí me puede llegar una garantía de un vehículo de un contrato pasado. Ya. Entonces, yo lo que puedo hacer esas búsquedas, por eso le digo complementarias, ¿ya? Ah, quiero buscar por entidad. Listo, escoge la entidad, pero adicional escoge la placa. Ah, en el caso que ahora les voy a explicar estrictamente para garantías, si debo seleccionar cuál era su contrato, inclusive ni siquiera seleccionarlo yo.

**Julián Perdomo:** Ah.

**DIANA:** Cuando yo lo busque en una lista desplegable me va a tener que decir, vea, era estas, estas y estas y estas órdenes que se trabajaron con tal e era bajo el contrato tal, bajo contrato tal a modo de lectura.

&nbsp;

&nbsp;

### **00:14:09**

&nbsp;

**DIANA:** si tiene que estar enlazado para yo saber cuándo fue que se trabajó, qué se le trabajó y bajo qué contrato, pero yo no tengo que ir a seleccionarlo. O sea, porque piensen en las chicas, o sea, las chicas no se van a acordar de que el contrato,

**Julián Perdomo:** No.

**DIANA:** el 5, el 10, el 20 y este vehículo cuando se le cambió el embraguega estaba en el contrato uno o en el contrato dos, ¿no? Eso tiene que ser estrictamente a modo de lectura. ¿Listo? Informativo. ¿Ven? Por eso, porque pienso que no debe ser un con un dato de búsqueda.

**Julián Perdomo:** Listo, Diana, ahí esta parte la entend.

**DIANA:** Listo, listo.

**Julián Perdomo:** Listo. Acá tenemos pues en este caso los campitos

**DIANA:** Mm.

**Julián Perdomo:** al que sería la placa, la sigla. Bueno, aquí ya que nos dices la sigla, pues es esa.

**Julián Perdomo's Presentation:** M.

**Julián Perdomo:** parte no la tenía, no la sabía yo. Yo pensaba que todos los carros tenían sign en este caso.

**DIANA:** No, solo los vehículos de policía. Por ejemplo, cuando tú estuviste acá,

**Julián Perdomo:** Al

**DIANA:** recuerda que, por ejemplo, hay acá hay contratos como CBC en Cali,

&nbsp;

&nbsp;

### **00:15:13**

&nbsp;

**Julián Perdomo:** sí

**DIANA:** medicina legal. Esos son carros que no tienen eh no tienen sigla. La sigla es exclusivamente para policía y seguridad y justicia.

**Julián Perdomo:** justicia. Listo,

**DIANA:** Entonces no puede ser un dato obligatorio. Bueno,

**Julián Perdomo:** listo.

**DIANA:** antes de que continúes,

**Julián Perdomo:** Dime.

**DIANA:** la parte en la que estaban haciendo ustedes que separaban cada historia de usuario estaba perfecto. ¿Qué era lo que pasaba?

**Julián Perdomo:** Sí,

**DIANA:** Que yo les pedía que hicieran porque aquí lo están dejando de manera general.

**Julián Perdomo:** sí.

**DIANA:** puede ser perfecto de manera general en el sentido de que nos vamos a dar una idea de cómo va a ser tarde o temprano la historia de usuario detallada, completamente detallada, donde ustedes se paran en el si van a hacer, por ejemplo, Scrom, creo que eso ya se los había explicado, en el sprintal vamos a a hacer la de eh crear roles, un ejemplo, la de iniciar sesiones. Entonces todas esas las van a dividir ya porque por ejemplo están roles, pero ustedes se tiene dentro del CRUD, ¿no? O sea, crear primero crear el rol, ¿ya?

**Julián Perdomo:** Oh.

**DIANA:** Luego eh yo puedo modificar ese rol o eliminar ese rol. ¿Listo? Y entonces las tres en dentro de un sprint o dentro de una empresa, uno hace uno no desarrolla las tres de manera inmediata.

&nbsp;

&nbsp;

### **00:16:39**

&nbsp;

**DIANA:** En el sprint uno dice,"Venga, voy a hacer esta vez solamente crear rol y dentro de ese sprint se dice,

**Julián Perdomo:** Sí.

**DIANA:** voy a crear el rol de, digamos, recepción, tal cosa, no sé qué la verdad." Cuestión de que al finalizar es el el el e el sprint, a su vez el Cuba sabe qué va a probar. Ah, yo tengo que probar el la creación de el rol de recepción. administración, contador y taller, un ejemplo. Ya.

**Julián Perdomo:** Aha.

**DIANA:** Y así mismo si mandan ajustes, ustedes saben sobre cuáles van a ser, porque si ustedes me dicen solamente crear rol, yo asumo que son todas. Entonces pueden la pueden dejar así parcialmente como está,

**Julián Perdomo:** ¿Cómo está?

**DIANA:** pero sí era mejor como estaba cada una independiente porque así nos va a dar una idea a futuro de más o menos cómo la van a empezar a desglosar es la palabra. Listo.

**Julián Perdomo:** Ah, listo, Diana. Igual esto como te digo es una propuesta, es un cambio de formato que nosotros hicimos porque digamos que las originales nosotros

**DIANA:** Sí, no hay inconveniente.

**Julián Perdomo:** las tenemos y las podemos modificar pues con base a lo que ya hemos trabajado.

**DIANA:** Mm. Y yo en el documento en el documento que yo les compartí, CD dieron cuenta, yo les seguí manteniendo y les dije, esta era eh y les hice una tabla pequeñita y les dije, esta era la hua,

&nbsp;

&nbsp;

### **00:18:09**

&nbsp;

**Julián Perdomo:** Sí.

**DIANA:** entonces les dije, para mí debería quedar así. Entonces también se llamaba 001 y entonces decía crear tal cosa y entonces ahí estaba ya porque a su vez a futuro dentro del sprint ah yo dentro de esta primero

**Julián Perdomo:** Ah.

**DIANA:** H001 yo tenía, voy a ponerles el ejemplo de la calculadora. Entonces en el primer yo dije voy a hacer el sumar y el restar. Entonces mi primer sprint va a ser sumar y restar. Luego en el segundo dije no, yo voy a hacer la multiplicación porque es más difícil. No sé qué laá va a estar esa ya. Y y ¿a quién voy? Deben de ser detallistas porque ustedes saben que no es lo mismo sumar dos números positivos a sumar dos números negativos o en guiño guillo a sumar uno positivo y uno negativo, que realmente no es una suma, sino una resta. Ya, pero eso, ah, venga, yo voy a programar la función de sumar dos números positivos. Ah, luego dentro del sprint voy a sumar dos números negativos. Ya. Entonces, eso es lo que tienen que ir que ir mirando. ¿Listo? Entonces, sí,

**Julián Perdomo:** Listo.

**DIANA:** lo vamos diciendo para que ustedes lo vayan puliendo. Vale,

**Julián Perdomo:** Vale, vale.

&nbsp;

&nbsp;

### **00:19:20**

&nbsp;

**Julián Perdomo:** Sí, eso lo tenemos en cuenta.

**DIANA:** listo,

**Julián Perdomo:** Eh, listo.

**DIANA:** listo.

**Julián Perdomo:** Acá pues teníamos acá teníamos una parte de que lo que sí, por ejemplo, mm pero ya con lo que nos dijiste del tema del de los contratos a mí me puso a pensar este selector ese es este acá nosotros lo lo planteamos en el sentido de que de que

**DIANA:** Mhm.

**Julián Perdomo:** una placa de un vehículo puede estar en varios contratos al tiempo. Entonces,

**DIANA:** Sí,

**Julián Perdomo:** si se hace caso,

**DIANA:** perfecto.

**Julián Perdomo:** pues eh la recepcionista o sí, la recepcionista debería seleccionar el contrato o de qué Sí, a qué contrato a qué contrato iría. Pero no sé, ya con lo que nos dijiste que la persona no debería tener eso,

**DIANA:** No, no.

**Julián Perdomo:** pues ya me puso a pensar.

**DIANA:** Cuando hablamos de Cuando hablamos de recepcionista hablamos de Brenda, ¿no es cierto?

**Julián Perdomo:** Ajá.

**DIANA:** Listo. Brenda no en este instante no tiene ni siquiera en este instante tiene la

**Julián Perdomo:** es

**DIANA:** información de a qué contrato pertenece. Muchas veces ni siquiera a qué entidad pertenece. Ella veces nos pregunta de venga, ¿es por policía o por seguridad y justicia?

&nbsp;

&nbsp;

### **00:20:40**

&nbsp;

**DIANA:** Listo. Por eso les sigo insistiendo de que debe ser por la placa. Si ese vehículo, pero te digo que sí puede ser en conjunto en conjunto a la placa AC de 1 2 3 eh dice que es eh le puede pertenecer a Policía o a Seguridad y Justicia y es el único caso. De resto, medicina legal, no sé qué. los otros nunca vas a tener. ¿Será medicina legal A o medicina legal B? No, medicina legal es medicina legal. En Cali es en Cali, listo.

**Julián Perdomo:** Es un a uno.

**DIANA:** Solamente pasa por policía. Entonces puedes decir,"Ah, la placa ahí sí puedes decir que una búsqueda compartida como para que me entiendan, ah,

**Julián Perdomo:** Sí.

**DIANA:** esa placa tiene dos entidades, la puedo meter por policía o la puedo meter por seguridad y justicia." Entonces, a modo de, por ejemplo, de verlo así rápido, en teoría ella puede escoger cualquiera de las dos entidades porque al fin y al cabo que quien decide bajo qué eh entidad queda es si trae orden ahí de una le dice, vea, es por seguridad y justicia. Si no trae orden,

**Julián Perdomo:** Aha.

**DIANA:** que fue lo que les mandé a cambiar, si no trae orden, ella puede escoger cualquiera. Y acá cuando nosotros hacemos la cotización, preguntamos por dónde quiere que ingrese, si por policía o por seguridad y justicia.

&nbsp;

&nbsp;

### **00:22:12**

&nbsp;

**DIANA:** Y los eh supervisores de cada entidad nos dicen,"No, necesitamos que entre por policía." Entonces, yo ya le cambiaría a policía y policía, apenas yo le escojo a policía, él automáticamente me tiene que traer. Ah, policía en este instante está en el contrato cuatro, un ejemplo. Ya. Ah, no, me están pidiendo que por seguridad y justicia. Ah, pues yo lo selecciono. Eso ya sería algo de la administradora. Ah, le selecciono que por seguridad y justicia a ese va en el contrato ocho. Un ejemplo. ¿Listo? Ese a modo información. El contrato yo no lo tengo que seleccionar, ni siquiera la chica de acá, o sea, Valentina y Daniela.

**Julián Perdomo:** Eh,

**DIANA:** Listo.

**Julián Perdomo:** pero Entonces, la coordinación, ¿cómo hace para para decir este contrato pertenece a perdón, este vehículo pertenece a este contrato? Es el día.

**DIANA:** Mira, te explico dos cosas porque esa duda precisamente la aclaré esta mañana porque yo tengo mi documento con esas.

**Julián Perdomo:** Sí, sí.

**DIANA:** Resulta acontece que si hablamos de las otras entidades, medicina legal, el SENA, CBC y eso, entonces es una sola entidad. es una sola entidad,

**Julián Perdomo:** Sí.

**DIANA:** por ende, en este momento tiene un solo contrato activo.

&nbsp;

&nbsp;

### **00:23:40**

&nbsp;

**Julián Perdomo:** Activo.

**DIANA:** Entonces,

**Julián Perdomo:** Ajá.

**DIANA:** ese vehículo sí pertenece a esa sola entidad bajo ese contrato activo.

**Julián Perdomo:** Sí.

**DIANA:** Los casos especiales,

**Julián Perdomo:** Pues ahí va.

**DIANA:** el caso especial es estrictamente policía y seguridad y justicia. Los vehículos pueden pertenecer a policía, policía o a la parte que nosotros llamamos seguridad y justicia. E inclusive aquí hay veces por los tipos de contrato ellos dicen,"Venga, este carro es de policía." O sea, legalmente pertenece a policía policía, pero yo no necesito que entre por policía, sino que necesito que me ingrese por seguridad y justicia. es el único caso que son especial. La los que tienen esas siglas sobre todo se pueden poner en cualquiera de los dos. Ya en la primera vez el contrato dice,"Venga, en este contrato van a estar estos y estos y estos vehículos y pertenecen a policía. Estos pertenecen, por ejemplo, a un demo, un ejemplo, que es lo de las tanquetas y eso. Pertenece a seguridad y justicia, pertenece a alcaldía, pertenece a tal cosa, tal cosa, a tal cosa. Ya, pero vuelvo y les digo, pueden moverse y y para qué es el contrato para saber bajo qué corte y a

**Julián Perdomo:** Uite

**DIANA:** qué empresa o cómo es que les voy a generar la factura.

&nbsp;

&nbsp;

### **00:25:11**

&nbsp;

**DIANA:** Por eso les repito, ese es el único que a futuro yo le voy a poder, la coordinadora le va a poder decir,"Señor supervisor, le llegó el vehículo AC 1 2 3\. Eh,

**Julián Perdomo:** Sí.

**DIANA:** sí, oy, por eso les digo y escuchen esto. Sí. Y solo sí o él llega con una orden, esa orden que viene en física o digitalizada le dice, por ejemplo, si aparece la orden si sega, siega, no me acuerdo bien cómo se pronuncia en este momento, ahí dice que es policía. Ah, si viene otra, si viene ese mismo vehículo y dice alcaldía, creo que es que dice, o seguridad y justicia, en ese momento voy a meter el carro por seguridad y justicia. Ya, pero si no llega con orden,

**Julián Perdomo:** Pero

**DIANA:** que es un vuelvo y le repito, fue un ajuste que yo les mandé a ustedes, que el vehículo debería permitir ingresarse,

**Julián Perdomo:** sí.

**DIANA:** así llegue sin orden para poderle realizar un diagnóstico para que yo ese diagnóstico se lo pase a la empresa, ya sea a policía o a seguridad y justicia, que es el que más está haciendo ese, y decirle, vea, este es el ajuste que se le va a realizar, apruébenlo o No, apruébeno. Si ellos dicen apruébenlo generan la orden y todo lo demás.

&nbsp;

&nbsp;

### **00:26:34**

&nbsp;

**DIANA:** Ya que sí debería ser, repito, y estoy de acuerdo, debería tener una entidad, ¿sí? ¿Quién no lo dice la primera vez el contrato? Entonces, por eso les digo, si algo ponen la placa, la entidad la trae, si quieren, entonces la trae por defecto, pero a la parte de la coordinación administrativa, déjenle que ella pueda escoger a qué entidad le va a cobrar eso. Ah, venga. Por más de que esté en policía,

**Julián Perdomo:** Sí.

**DIANA:** me están pidiendo que lo meta por seguridad y justicia. No es necesario que se cambie en la base de datos a el vehículo ABCD, perdón, ABC 1 2 3 pertenece a policía. No, lo que va a hacer es a facturarse en seguridad y justicia. De pronto ahí no me expliqué. O sea, esa parte es hacia hacia dónde se va a facturar, no es hacia quién pertenezca. Esa es la diferencia. Ah, ahora el vehículo AC 1 2 3 que pertenece estrictamente a policía, se va a cobrar por tal parte, se va a cobrar por la parte A o por la parte B. Más vale es por ese lado. O sea, sí tienes razón de un vehículo pertenece sí y solo sí a una sola entidad. ¿A quién? ¿A policía o a seguridad de justicia?

&nbsp;

&nbsp;

### **00:28:03**

&nbsp;

**DIANA:** o un momento,

**Julián Perdomo:** M.

**DIANA:** pero sí lo puedo cobrar en cualquier otro contrato o al cualquier otra entidad con el contrato activo. Y eso es lo que deberíamos permitir modificar en la parte administrativa, no acá en la parte del ingreso. Entonces, en la parte del ingreso que vemos mejor de que la recepción ingresa la placa y siempre va a decir,"Es policía." Ah, listo. Mándelo así, lléguele la información a la administración. de que el vehículo ABC pertenecía a policía, el vehículo talía pertenecía a medicina legal, ¿ya?

**Julián Perdomo:** Okay.

**DIANA:** Ah, no, que el de policía, que es el que tiene conflicto. Entonces, la coordinadora ya mira y dice,"Ah, sí, sí lo vamos a manejar por policía." Ah, no, cuando vayamos a facturar, facturar no va a ser por policía, sino que va a ser por seguridad y justicia. Pero entonces el vehículo no va a modificar a quién pertenece o quién es su dueño, la entidad dueña, sino simplemente la facturación. ¿Listo? Esa es como debe quedar.

**Julián Perdomo:** Listo.

**DIANA:** Listo.

**Julián Perdomo:** Bueno, acá teníamos el tema del inventario por entidad. formatos. Permitir configurar y asignar formatos de ingreso y salida para cada entidad, asegurando que se visualicen los campos requeridos y una lista simple

&nbsp;

&nbsp;

### **00:29:34**

&nbsp;

**DIANA:** Mhm.

**Julián Perdomo:** eh opcional o requerida según la configuración. ¿Listo? Eso es en el caso, por ejemplo,

**DIANA:** Eso es.

**Julián Perdomo:** de los formatos de las entidades que tienen formatos propios de entrada y salida, ¿no?

**DIANA:** Mm. Sí,

**Julián Perdomo:** Seguridad y justicia cuando tiene

**DIANA:** esos esos formatos que veo que lo de pronto, ¿qué es lo que hace más falta ahí? más allá de registrar un checklist y eso es tengan presente hay

**Julián Perdomo:** Sí,

**DIANA:** veces que se ellos ya tienen un formato establecido.

**Julián Perdomo:** sí.

**DIANA:** Entonces por eso yo por ahí les colocaba a ustedes que permitir configurar esos formatos.

**Julián Perdomo:** Sí.

**DIANA:** Entonces debe haber por allá en una parte donde yo diga configurar para los vehículos de ejemplo medicina legal, ellos quieren este formato de ingreso. Entonces, yo debo poder o cargar, en teoría cargar ese documento si digamos que me lo mandaran y yo lo escaneo y permitirlo diligenciar así sea a mano dentro de la tablet, digamos, o dentro del dispositivo de ay, dice que viene con combustible y entonces es un checkbox y el ah sí, venga, yo le puedo dar ese click de que sí. Ay,

**Julián Perdomo:** Yes.

**DIANA:** de que escríbame el kilometraje con el que ingresó.

&nbsp;

&nbsp;

### **00:30:50**

&nbsp;

**DIANA:** No, no, no. Escríbame si el vehículo llegó con radio. Ah, llegó con radio. Ya. No todas las empresas primero solicitan ese formato. Segundo, no es el mismo formato para medicina legal que para la policía o para CBC.

**Julián Perdomo:** Bien.

**DIANA:** Cada uno tiene su propio formato. Por eso cuando yo les puse y les revisé esa historia de usuario, les dije,"Por favor, que sea configurable o en su grandísimo defecto, eso no se los puse, pero pues lo pueden hacer. Es si me van a entregar un documento, que puede ser un documento en un texto plano o un sí, ah, que no, que es un Excel o un CBC o algo que yo lo pueda subir, pero a su vez que lo pueda editar. ¿Listo? más allá de de eso, porque no siempre voy a poder eh hm h, ¿cómo se llama? Seleccionar las cosas porque yo dije que era así, ¿no? Esos formatos eh cuando las empresas crean formatos, ellos pasan por unas revisiones dentro de sus dentro de su institución y

**Julián Perdomo:** Pas.

**DIANA:** es ese formato tal cual. Si si tiene el logo a la derecha siempre va a estar en la derecha, en la izquierda, en lo que sea, o sea, como lo digan ellos, yo no puedo entrar a modificárselos y entonces por eso les digo que sea configurable esa parte.

&nbsp;

&nbsp;

### **00:32:21**

&nbsp;

**Julián Perdomo:** Listo, listo. Por aquí tenemos una validación que fue la que nos dijiste que se implementaron validación estricta que

**DIANA:** Mhm.

**Julián Perdomo:** compara un nuevo valor, un nuevo kilometraje ingresado con el anterior, generando una alerta si el valor es menor.

**DIANA:** Listo. Por ejemplo, ya lo han pensado, ¿cómo lo van a hacer dentro del prototipo? ¿Qué es lo que ustedes a tienen que ir pensando? ¿Van a generar un campo, dos campos, mensaje, no mensaje?

**Julián Perdomo:** Eh, la idea sería un campo a visualizar o o sea sería sería M. tener un un campo donde diga el valor anterior o en su defecto podría ser ingreso un que un un valor que que no cumpla con o bueno, que que pueda generar un error pues que tiene una una alerta, pero bueno, sí sería bueno.

**DIANA:** Es es es mejor la alerta. Es mejor la alerta. Y creo que yo ahí se las puse. Es mejor la alerta. Entonces ustedes ingresan, por ejemplo, el vehículo ya ha ingresado y antes tenía, pongamos 10\. 10\. Voy a hacer el camino feliz, ¿eh? Y puse 15\. Perfecto. Él continúa, no me va a mostrar mensaje ni nada, pero por alguna razón yo puse no más uno.

&nbsp;

&nbsp;

### **00:33:44**

&nbsp;

**DIANA:** No alcancé a poner el 15\. Si yo le pongo uno, apenas yo le dé enter o pase al siguiente con tab o lo que sea, al siguiente campo que voy a llenar o que se va a llenar o algo. Entonces de una muestra una alerta, un mensaje, o sea, diciendo eh kilometraje no válido o

**Julián Perdomo:** Alo.

**DIANA:** kilometraje menor al último.

**Julián Perdomo:** No.

**DIANA:** Es necesario que yo tenga otro campo adicional porque me va a cargar de manera visual. Entonces, yo estoy pensando ya en la experiencia del usuario. Me va a cargar eso en el mensaje. Le puede decir el kilometr el último kilometraje era 10\. Ya. Cuando y las validaciones que tú dices si es uno no válido, no valorable que por alguna razón puse \-1. Ah, pues de esa misma alerta utilizan el mismo popup, ¿ya? o que puse 10.5, ¿no? Porque pues los kilómetros son exactos, entonces no válido porque ya puso el punto. Listo.

**Julián Perdomo:** E listo.

**DIANA:** Listo. Pero y por eso ahí dice se implementará una validación, por eso es validación. No es necesario visualizarlo o tener otro otro

**Julián Perdomo:** Campo ahí.

**DIANA:** campo, simplemente con una validación estricta.

&nbsp;

&nbsp;

### **00:35:09**

&nbsp;

**Julián Perdomo:** Eh, listo. Acá tenemos pues en este caso lo que nos dijiste quería que el vehículo puede ingresarse en una orden de trabajo externa.

**DIANA:** Sí, perfecto.

**Julián Perdomo:** eh se habilitará mediante un flujo de checos que exija un diagnóstico

**DIANA:** Mm,

**Julián Perdomo:** obligatorio antes de solicitar la orden.

**DIANA:** sí, perfecto. Mm. Pero el checkbox,

**Julián Perdomo:** Si el vehículo no es

**DIANA:** ojo que el checkbox es para no exigir el diagnóstico. Yo les de pronto ahí no les dije, pero entonces está el formulario o no recuerdo si les expliqué bien, está el formulario que Brenda hace. Entonces Brenda le pregunta al conductor y le dice,

**Julián Perdomo:** Sí.

**DIANA:** "Ven, ¿traes orden?" Y él dice,"No, no traigo el ahorro porque él viene para diagnóstico y luego se hace la orden." Un ejemplo.

**Julián Perdomo:** Sí.

**DIANA:** Ya. Entonces, ese checkbox es el que Brenda va a seleccionar y el título del este es con orden o sin orden. Entonces, digamos que así o puedo ponerle solamente orden externa, porque esa es la orden externa. Si la selecciono significa que sí trae orden y ahí debe permitirse de pronto h desplegar un campito para cargar la orden. ¿Listo? Pero si no la selecciono, él me debe permitir el flujo y pues obviamente no se me va a mostrar un campito adicional donde yo vaya a cargar orden porque no seleccioné y pues Brenda va a poder ser registrado, ingresado y se va a la coordinación.

&nbsp;

&nbsp;

### **00:36:46**

&nbsp;

**DIANA:** le va a llegar un mensaje diciendo vehículo ingresado sin orden y ese es ahí es donde se dice que estrictamente viene para diagnóstico, pero quien envía y que se dice que sea estrictamente para diagnóstico es porque no tiene orden. Ahí está bien. Pero el checkbox no es que me obligue al diagnóstico, no. El checkbox será en el formulario de recepción que me diga con orden o sin orden y ese me permita cargar la orden o no me permita cargar la

**Julián Perdomo:** Listo,

**DIANA:** orden.

**Julián Perdomo:** listo. Ese sí lo teníem. Lo vamos a listo. Si no está registrado el vehículo, la recepcionista ingresará los datos disponibles, notificará coordinación y el vehículo quedará bloqueado hasta la valiación de la de la

**DIANA:** Sí,

**Julián Perdomo:** coordinación administrativa.

**DIANA:** sí. Perfecto,

**Julián Perdomo:** Eso en este caso,

**DIANA:** ese sí está bien.

**Julián Perdomo:** eso pues fue en el caso de que, por ejemplo, no estuviera en la en el lista de vehículo y no estuviera en la oferta tampoco, ¿vale?

**DIANA:** Sí, que nos está pasando en este momento. Mhm.

**Julián Perdomo:** Vale, acá tenemos el tema de la captura de firmas, que en el caso del conductor pues se debe entregar el conductor debe firmar, ya sea que Brenda pues le por medio de la tablet o algo.

&nbsp;

&nbsp;

### **00:38:07**

&nbsp;

**Julián Perdomo:** Y en el caso de la recepcionista pues esto debe haber una configuración previa, ¿no? Se utilizará la opción usar firma a un clic, es decir, ella no va a firmar, sino que usa la firma que tiene configurada.

**DIANA:** Sí, exacto. O sea, Brenda dice firmar y da clic en firmar y ya queda firmado. Tanto el de él como el de ella. Sí.

**Julián Perdomo:** Sí,

**DIANA:** Mm.

**Julián Perdomo:** listo. Tenemos aquí el tema de la notificación,

**DIANA:** Inclusive, inclusive ni siquiera es necesario si nos ponemos a pensar,

**Julián Perdomo:** ¿no?

**DIANA:** porque como tenemos un usuario,

**Julián Perdomo:** que se tome.

**DIANA:** o sea, con ese rol, entonces ya cuando Brenda le diga registrar, por debajo va y le pone la firma que ya tiene o vehículo ingresado, por debajo ya va y le pone la de Brenda porque era ese usuario registrado. No. O sea, digamos que ya no es solamente Brenda, digamos que tenemos tres personas de ingreso, Brenda,

**Julián Perdomo:** Sí.

**DIANA:** María y Petra. Entonces,

**Julián Perdomo:** Sí.

**DIANA:** si Petra está ingresando, pues ella cuando le de ingresar vehículo por debajo ya va y le pone ese usuario porque ya sabemos que es que es Petra. Ni siquiera es necesario un botón de firmar.

&nbsp;

&nbsp;

### **00:39:23**

&nbsp;

**DIANA:** Con eso se sobrecarga el formato, la visual del del usuario no es tan necesaria.

**Julián Perdomo:** Eh, listo, esa parte la vamos a corregir. Eh, tenemos el tema de las notificaciones que se notificará mediante un evento de generación al al coordinador administrativo y al jefe de taller. notificaciones pues se harán mediante correo, eh, mediante WhatsApp correo y una alerta, una campanita que pueda tener la aplicación ahí.

**DIANA:** Listo. Perfecto.

**Julián Perdomo:** Aunque aunque esto aquí es el tema de las notificaciones aquí pues es más como un llamado a la bandera, diría yo, ¿no? Porque el taller o bueno, no sé ellos si lo han hablado,

**DIANA:** Sí,

**Julián Perdomo:** deberían de tener un sistema de comunicación más más directo, ¿no? Ya sea por teléfono o algo así.

**DIANA:** pero se le va a decir, sí, también. Y se puede que llegue como mensaje de texto. La vaina es que, por ejemplo, tienes que tener en cuenta que hay veces se sobrecarga, ¿no? Pero sí debería ser por todos los medios,

**Julián Perdomo:** Sí.

**DIANA:** o sea, que la aplicación se asegure que sí se informó. Sí. O sea, que si lo quieren, que lo si lo hacen a todos mejor. Ah, que lo hace al correo,

&nbsp;

&nbsp;

### **00:40:38**

&nbsp;

**Julián Perdomo:** Ok.

**DIANA:** que lo hace al WhatsApp, que lo hace al celular de, es decir, el al mensaje de texto, ya que la aplicación tiene una sección de de notificaciones y tiene un circulito ahí que le dice que tiene una notificación nueva. Sí, que le aparece como en los celulares que es eh que se despliega una barrita adicional también que le genera otro popup a la otra persona, una alerta así a la derecha, a la izquierda, que le sale como el chat que le sale para arriba, para la izquierda, todas las que ustedes quieran, porque el objetivo es que la aplicación asegure que sí le está notificando a la persona que el vehículo llegó.

**Julián Perdomo:** Eh, listo. Bueno, acá tenemos por apartado de criterios de aceptación. Eso pues no eh hasta donde supe en la última reunión pues nos hiciste un poquito de énfasis en ese tema. Detallar detal. Eh, aquí nosotros pues colocamos ese listado e al digital la

**DIANA:** Hola.

**Julián Perdomo:** placa o Dale,

**DIANA:** Dame un minuto. No te escucho.

**Julián Perdomo:** eh. M.

**DIANA:** Ah, ya.

**Julián Perdomo:** Listo.

**DIANA:** Que apenas es que fue la señal por acá.

**Julián Perdomo:** Ah, bueno, tenemos estos íems. Eh, primero pues registrar la placa de un vehículo registrado.

&nbsp;

&nbsp;

### **00:42:11**

&nbsp;

**Julián Perdomo:** Eh, y al digital avanzar el campo del sistema consulta los datos, entidad y carga automáticamente modo lectura. Listo.

**DIANA:** Mhm.

**Julián Perdomo:** Eh, al identificar la entidad se despliega, bueno, esto se despliega automáticamente el formato de ingreso y de inventario configurado especialmente eh para los requisitos de esta entidad. Bueno, eso hay que verlo porque según lo que nos dijiste, hm, hay que ver cómo se por el tema de los formatos.

**DIANA:** Mhm.

**Julián Perdomo:** Tenemos esta que es eh al ingresar el kilometraje actual, el sistema ejecuta una validación en tiempo real. Si el valor es menor al último registrado, pues muestra un mensaje de alerta bloqueante, pues,

**DIANA:** Mhm.

**Julián Perdomo:** o más que es como una notificación. Listo. Esta palabra eh al marcar el checkbox de ingreso sin sin orden externa, el sistema habilita un flujo de diagnóstico. Bueno, esto de diagnóstico obligatorio ya que nos dijiste, pues es más como más el tema de de dejar pasar el vehículo sin órdenes.

**DIANA:** Sí,

**Julián Perdomo:** Ajá.

**DIANA:** sí. ¿Por qué? Porque es que mira que él cuando ustedes dicen allí y como se lee

**Julián Perdomo:** Ajá.

**DIANA:** es diagnóstico obligatorio, es decir, que pasa de una diagnóstico, ¿no?

&nbsp;

&nbsp;

### **00:43:40**

&nbsp;

**DIANA:** Él debe pasar por es de batería debe pasar por coordinación para que la coordinación sepa, ah, venga, yo voy a tener un diagnóstico y de ahí debo hacer una cotización. Por eso es que sí es obligatorio que le hagan el diagnóstico, pero no es obligatorio que pase de una, no, él debe pasar por coordinación, o sea, que debe seguirle mostrando el mensaje a coordinación y coordinación. Ah, listo. Este va para enviar, para realizar diagnóstico. ¿Por qué? Porque va pasado también. Entonces, eh de que entra eh ah, llegó el vehículo, no sé qué y ya uno medianamente conoce y dice,"No, este vehículo no puede ingresar por aquí por policía o por seguridad y justicia o no, realmente no le van a hacer, no le van a hacer nada, ya se va a ir de baja. Entonces, ¿para qué pongo a hacer un diagnóstico?" Entonces, ten en cuenta y ten presente que la única persona que solicita los diagnósticos es la coordinadora administrativa.

**Julián Perdomo:** Ajá.

**DIANA:** ¿Listo? Entonces,

**Julián Perdomo:** Es

**DIANA:** por eso debe pasar, pero si es obligatorio el diagnóstico, sí, en el sentido de como Pero no así tan de una, si no no te saltes el paso de coordinación.

**Julián Perdomo:** listo.

**DIANA:** Mhm.

**Julián Perdomo's Presentation:** M.

&nbsp;

&nbsp;

### **00:44:58**

&nbsp;

**Julián Perdomo:** Mala notificación. el el tema que te habíamos hablado, eh si un vehículo pues no está registrado, guarda la información proporcional que el vehículo operativamente y y la coordinación, alertan la coordinación para su avaliación. Bueno, eso fue lo mismo y ahora

**DIANA:** Okay.

**Julián Perdomo:** y listo. Creería yo que más o menos eso es lo que

**DIANA:** Sí, sí, eso es más o menos los ajustes que yo les dije. Pero miren,

**Julián Perdomo:** Ajá.

**DIANA:** miren que díganme y díganme honestamente ustedes, por ejemplo, ahí les es claro, por ejemplo, eh, digamos el de el que estamos hablando, el de al ingresar el kilometraje actual, el sistema ejecuta la validación en tiempo real si el valor es menor al último ingresado. Ese es un criterio de aceptación.

**Julián Perdomo:** Sí.

**DIANA:** Si tú subes, el eh a ustedes les queda completamente claro, por ejemplo, eh solo existe para esta historia de usuario. ¿A qué voy? A que recuerden ustedes que ustedes tenían separadas las cosas. Sí,

**Julián Perdomo:** Sí.

**DIANA:** me acuerdo que tenían eh eh historia de usuario

**Julián Perdomo:** H.

**DIANA:** 01\. Exacto. Ya. Entonces, ¿por qué voy?

&nbsp;

&nbsp;

### **00:46:19**

&nbsp;

**DIANA:** Porque por ejemplo, honestamente el de el kilometraje debería ser sí y solo sí otra historia de de usuario. Ya, pónganle a la grande historia,

**Julián Perdomo:** un

**DIANA:** pónganle a pongámosle así, historia de usuario 1 o 001, la creación del vehículo,

**Julián Perdomo:** Sí.

**DIANA:** pero él tiene otras subhistorias de usuario.

**Julián Perdomo:** Sí.

**DIANA:** Entonces, la primera va a ser es consultar una placa o ingresar una placa. Entonces, va a ser 001 raya un consultar la placa tal o cuando yo ingrese la placa tal me traiga el vehículo. ¿Listo? Ahora,

**Julián Perdomo:** Mhm.

**DIANA:** por ejemplo, ahora con ese del kilometraje a pertenece a la uno,

**Julián Perdomo:** Ok.

**DIANA:** pero va a ser eh historia de usuario 001, rayita 2, validación del kilometraje, porque analicen lo que él él va a tener sus propios criterios de aceptación y no es solamente el único de que me valide si es un valor menor al ingresado. Realmente me debe validar si es un número correcto. Y ya les di el ejemplo, porque el usuario me puede escribir por error menos 10,000, pero fue porque se le fue por error. Pero el software me debe asegurar que informa o no deja pasar esos errores.

&nbsp;

&nbsp;

### **00:47:46**

&nbsp;

**DIANA:** Ah, que sin querer escribió eh 10.50. Ah, no, ese no es un kilometraje válido. Entonces, ese debería ser una historia de la pueden mantener como tenían antes para que les sea más

**Julián Perdomo:** Yeah. Vamos a

**DIANA:** claro cada criterio de aceptación. ¿Listo?

**Julián Perdomo:** listo. Entonces,

**DIANA:** O lo hacen como se o lo hacen como se los acabo de mencionar, tal como la tienen aquí de manera general o la arriba, la parte general, ¿qué vamos a hacer? Vamos a ingresar un vehículo. ¿Quién lo va a hacer? Ah, lo va a hacer la recepcionista dentro de la narrativa. No sé si recuerdan el documento que les les pasé dentro de la narrativa. Eh, ah, ¿por qué lo vamos a hacer? Pues porque ahorita se está haciendo de manera manual y lo queremos de manera digitalizada. ¿Listo? Eh, ¿cuáles van a ser los criterios de aceptación? Que un vehículo tal cosa que bla bla bla bla. Ahora sí, esa era la uno. Si quieren le ponen A, B, C. Yo no me acuerdo si yo les puse veces así o no. Ah, la A, ¿cuál va a ser? Ingrese un vehículo existente.

&nbsp;

&nbsp;

### **00:48:54**

&nbsp;

**DIANA:** Ah, y ese es el camino feliz. El vehículo existe y de una me trae a qué entidad pertenece y me trae el kilometraje y la persona ingresó el kilometraje correcto y tenía orden y todo lo

**Julián Perdomo:** Ese

**DIANA:** demás. Ah, el el B o el dos. Voy a ingresar un docum un vehículo que no existe también. Ahí les falta, no lo veo allí. Un vehículo que no existe. Se los puse dentro de la historia que les mandé a a corregir.

**Julián Perdomo:** se nos

**DIANA:** ¿Qué pasa? ¿Qué pasa si el vehículo no existe? Ah, no, él debe ingresar. Ah, sí, sí, mentira. Sí, sí, lo vimos. Eh, que por allá,

**Julián Perdomo:** tenemos eh

**DIANA:** pero sí, pero dentro de los criterios, mira que los criterios de aceptación no está y eso debe ser un criterio de aceptación. Es una historia de usuario, pero es un criterio de aceptación. ¿Por qué?

**Julián Perdomo:** listo.

**DIANA:** Porque debe permitirse debe permitirse registrar o ingresarse y esperar a que la coordinación lo ejecute. Entonces debe decir, ah busca la placa, muestra un mensaje que no es así correcto, pero entonces no lo vamos a poner. ¿Quién lo va a hacer?

&nbsp;

&nbsp;

### **00:50:04**

&nbsp;

**DIANA:** Sabemos que ya es dentro de la misma, entonces no es necesario repetir de pronto el eh la narrativa. ¿Quién lo va a hacer? ¿Por qué lo va a hacer? No, no, de pronto es el porqué rápido de vehículo no existente. ¿Listo? Entonces, eh, ¿para qué? Para que quede en la base de datos. Ah, listo. ¿Qué se va a hacer? La persona ingresa los datos que pueda ingresar, porque si tiene la tarjeta del vehículo, ya va a poder ingresar la plata, eh, el color, el modelo, la marca y no sé qué. Y si tiene, si no tiene, porque hay veces que vienen acá sin esa tarjeta de propiedad, solamente ya ve físicamente que es un ejemplo,

**Julián Perdomo:** He.

**DIANA:** ya conoce, ah, eso es un Renault. Hm. Pero, ¿qué será? Logan Expression no sé qué nousteran. No, no sé nada. Ah, pues yo le pongo la placa y sé que es un logan, llena estrictamente esos datos y manda el mensaje a coordinación. Pero si ves que va a tener un criterio de aceptación, debe llenar al menos debe llenar al menos un dato y poderlo registrar. ¿Listo?

**Julián Perdomo:** Ev. Oi.

&nbsp;

&nbsp;

### **00:51:21**

&nbsp;

**DIANA:** Ah eh eh su otra historia de usuario va a ser carro sin orden. ¿Qué va a pasar? Ah, venga, sin orden es seleccionen un checkbox por allá. ¿Quién lo hace? La recepción. ¿Para qué lo hace? Que permita seguir y se le genere diagnóstico. Ah, ¿cómo va a ser? Eh, va a haber un checkbox por allá. Eso es dentro de las criterios de aceptación. un checkbox que diga orden. Si está seleccionada, si se selecciona, se carga la orden. Si no está seleccionada se asume o se dice que no trae orden y pasa y va a generar una notificación. Esos son los criterios de aceptación y yo traté de dárselos a ustedes de manera un poquito más desmenuzada porque aquí está de manera general, pero no va a ser claro.

**Julián Perdomo:** Un momentico.

**DIANA:** O sea, no sé si me Exacto. Ya no sé si tienen de pronto dudas frente a esto para que los hagamos. Y si se dan cuenta, si ustedes hacen esas cositas así detalladas,

**Julián Perdomo:** Aló.

**DIANA:** a la hora de que ustedes vayan a hacer el prototipo, ya lo tienen un poco más visualizado. Ah, el logo va a quedar en la derecha y en la izquierda,

&nbsp;

&nbsp;

### **00:52:29**

&nbsp;

**Julián Perdomo:** Sí.

**DIANA:** no sé qué. Y yo por allá voy a poner, no sé, a la derecha, a la izquierda, tengo que poner un checkbox que diga orden. Y si lo selecciono abajito tengo que desplegarle un icono que diga examinar o activar cámara para saber si le toma la foto o si me la envía por WhatsApp o me la envía por algún medio y se la debo cargar. Ya. Ah, no la seleccionado, pues no se me va a desplegar nada. y continúa. ¿Sí se dan cuenta que si los criterios de aceptación están un poco más definidos, el prototipo sale así?

**Julián Perdomo:** Hola, James. Buenas tardes. Muy bien, muy bien. Aquí recuperá por favor.

**DIANA:** Listo,

**Julián Perdomo:** Eh, dame un momentico.

**DIANA:** listo.

**Julián Perdomo:** Qué pena. Es verdad. Sí, señor. Eh, listo. Ahora sí podemos abordar el tema de lo que nos ibas a comentar.

**DIANA:** Listo. Les voy a proyectar pantalla. Todavía no he terminado.

**Julián Perdomo:** Dale,

**DIANA:** Les voy a hacer entrega parcial de algunas cosas.

**Julián Perdomo:** vale.

**DIANA:** Eh, yo estoy generando un documento que dice de qué documento venía de ustedes.

&nbsp;

&nbsp;

### **00:53:52**

&nbsp;

**Julián Perdomo:** Sí.

**DIANA:** Entonces, por ejemplo, dice asesor servicio y era creación de la recepción del vehículo. Listo.

**Julián Perdomo:** Sí, señora.

**DIANA:** También el jefe de taller y crear diagnóstico. las historias de usuario que que tenían antes ustedes. Entonces, la H05, la H01.

**Julián Perdomo:** Sí.

**DIANA:** Listo. Les estoy tratando de dar un semicontexto y la pregunta que tengo, las respuestas se las voy a dar de listo. ¿Qué es el objetivo de que quiere que se haga? ¿Listo? Por acá yo tengo eh el que más les puedo explicar así y para que ustedes vayan teniendo eh claridad, hay uno que se llama garantías.

**Julián Perdomo:** Eh, listo.

**DIANA:** ¿Qué se me hizo?

**Julián Perdomo:** donde se ellos allá no manejan ahorita un estándar, ¿no?

**DIANA:** No, pero yo ya lo, o sea, yo ya lo creé. Me tocó programarlo a las este tengo un documento Excel que yo se los voy a mostrar. Es un documento Excel que eh yo lo creé.

**Julián Perdomo:** Listo.

**DIANA:** ¿Qué estoy haciendo? Yo voy a borrarlo.

**Julián Perdomo:** Sí.

**DIANA:** Yo qué hago en este instante yo selecciono sí y la empresa porque como yo ya ellos vienen por garantía, significa que ellos ya el carro entró y ellos ya me dijeron,"Vea, entró por medicina legal." Ah,

&nbsp;

&nbsp;

### **00:55:15**

&nbsp;

**DIANA:** listo.

**Julián Perdomo:** Sí,

**DIANA:** O entró por policía o entró por seguridad y justicia, que es el que más conflicto genera. Ah,

**Julián Perdomo:** sí,

**DIANA:** me entró por seguridad y justicia. Entonces, yo selecciono y pongo la placa y él va y me busca.

**Julián Perdomo:** sí,

**DIANA:** O yo pongo,

**Julián Perdomo:** sí.

**DIANA:** por ejemplo, policía y busco, en este caso yo busco por sigla para la policía y pongo la sigla y eso en

**Julián Perdomo:** Sí.

**DIANA:** este caso, garantías, él me va a traer la orden de trabajo. Espérenme una placa. Voy a voy a buscar por medicina legal, que es como la más rápida para que lo miren ahí

**Julián Perdomo:** Dale.

**DIANA:** rápidamente. Medicina legal. Ese tiene por placa COVID 938\. Ah, espero que no se me demore. Él hace el proceso. Él va y busca. Listo.

**Julián Perdomo:** Sí.

**DIANA:** Ustedes a los usuarios siempre pónganles iconos que sepan qué están

**Julián Perdomo:** Ah,

**DIANA:** haciendo ya. Ay, ¿por qué no me lo encontró? Ay,

**Julián Perdomo:** ya una

**DIANA:** porque escribí mal la placa porque es Obi

**Julián Perdomo:** hora.

&nbsp;

&nbsp;

### **00:56:23**

&nbsp;

**DIANA:** 398\. Ya. Eh, yo no tuve el principio porque lo estaba haciendo yo y poco a poco de yo no tenía este esta carpetica que ese icono de cargando, entonces no saben cuándo es. Entonces, mírenlo, yo lo busco y él me dice,

**Julián Perdomo:** Sí.

**DIANA:** vea, ¿qué dependencia es o a quién pertenece a medicina legal? ¿En qué corte hoy? Es algo que casi no lo veo que no lo han manejado allá en las historias de usuario. Pertenece al corte uno. Ah,

**Julián Perdomo:** Sí.

**DIANA:** el contrato aquí en este momento no me está saliendo. Donde me lo veo veo un poco mejor es en policía. Ahora lo lo buscamos. Ah, listo. Medicina legal. Aquí como estoy utilizando datos de prueba, pues ella puso que el vehículo yo puse que más da y que la marca era Cherrolet. Obviamente pues eso no existe,

**Julián Perdomo:** Sí.

**DIANA:** ¿no? Pero pues aquí para pruebas. Ah, total facturado y eso. Entonces él me trae la orden de trabajo porque tengan en cuenta que esta orden de trabajo es orden de trabajo interno de nosotros,

**Julián Perdomo:** Sí,

**DIANA:** una orden que en este momento nosotros creamos.

**Julián Perdomo:** sí.

&nbsp;

&nbsp;

### **00:57:29**

&nbsp;

**DIANA:** Ah, y me dice orden tal. Y esto es lo que se le hizo al vehículo. Me en este me permite,

**Julián Perdomo:** Sí.

**DIANA:** yo tengo un acceso al link donde me permita ir a ver la orden, lo que tiene, qué es lo que tiene de manera real. Ah, tiene esto, no sé qué. Ah, mira, por acá tiene el total. Yo por acá lo tenía total facturado. Ah, sí, sí me lo trae eh el vehículo, la marca Chevrolet, el corte y eso.

**Julián Perdomo:** Sí.

**DIANA:** Listo. Cheolet. Sí,

**Julián Perdomo:** Sí.

**DIANA:** Cherolet. Sí. Do I don't good. Listo. Y me trae cuándo salió. Miren que acá. ¿Por qué? Tengan en cuenta que las garantías es a partir de la fecha de salida. Entonces, ah, ve kilometraje de origen, el me trae el kilometraje el último con que ingresó, o sea, con esta orden se creó y tenía este kilometraje.

**Julián Perdomo:** Sí.

**DIANA:** Aquí me dice, ay, perdón, aquí me dice cero, eh, menos no sé cuánto porque yo aquí no le he ingresado. Entonces, miren la validación. Entonces, por ejemplo, si yo pusiera, ah, no, esa no la he terminado de hacer.

&nbsp;

&nbsp;

### **00:58:37**

&nbsp;

**DIANA:** Si yo pongo 10, pues miren que no está cambiando. Él me sigue mostrando en menos. Pongámosle un número un poquito para que cambie, ¿eh? Miren lo que ahí cambió a 23\. Ya. ¿Qué es lo que yo me falta para terminar de programarlo?

**Julián Perdomo:** Sí.

**DIANA:** Venga, ese no es incluimetraje correcto porque está siendo menor. Yo aquí lo tengo todavía en menos, pero yo le puedo poner aquí dentro de este Excel un mensaje a través de de programación de no, venga, es incorrecto porque está menos de con el cuando él me ingresó a la acá que se le hicieran todos estos ajustes. Listo. Lo mismo inclusive, no sé si alcancen a ver los días transcurridos. Yo, por ejemplo, él me dice que él salió el 28\. Entonces,

**Julián Perdomo:** Seguí.

**DIANA:** ¿cuándo ingresa? Digamos que ingresó el 30 de del mes 09 del 2026\. Ah, por tiempo, días transcurridos lleva 33, digamos. Ah, digamos que yo aquí solo hubiera tenido eh batería. Ah, pues una batería tiene garantía por ahí un año. Un ejemplo. Ah, han pasado 30 días. Pues sí, debo darle garantía.

&nbsp;

&nbsp;

### **00:59:53**

&nbsp;

**DIANA:** por esa por eso yo tengo aquí aplica garantía. Entonces yo, por ejemplo, voy a decir sí o no. Entonces yo voy a hacer unas validaciones por acá de decir, ay, venga, el cambio del aceite, un ejemplo, fue hace 33 días, pues no,

**Julián Perdomo:** Sí.

**DIANA:** eso dice que es por kilómetro, 5,000 km o al año. Yo hago la validación y va a decir,"Sí, si aplica garantía, tienen que hacerse." O,"Ah,

**Julián Perdomo:** Sí.

**DIANA:** no, ya se pasó." No, no aplica ya. Ah, o por ejemplo el de la batería.

**Julián Perdomo:** Eh, sí.

**DIANA:** Ah, no, la batería, digamos era un año y ya han pasado 367 días, ¿no? Pues no le aplica ya para eso.

**Julián Perdomo:** Sí.

**DIANA:** Eso es algo que ustedes no lo tien y en este momento eh pues estoy programando eso porque

**Julián Perdomo:** en el taller. Hecho. Creo que tampoco

**DIANA:** están están llegando las garantías que ustedes quieran. adicional acá, pues acá voy a tener unos ítems que me va a decir ítem uno de nuevo.

**Julián Perdomo:** Seg.

**DIANA:** Ah, pues me tocó ponerle más aceite.

&nbsp;

&nbsp;

### **01:00:54**

&nbsp;

**DIANA:** Pues el aceite que tengo que ponerle, ¿cuántos eh cuartos de aceite le cambié? Eh, ah, bueno, aquí una unidad eh la si es en litro, en cuartos, unidad, juego y eso que eso está dentro de las ofertas. ¿Cuántos gasté? el valor que en teoría me terminó de costar ese repuesto y acá el valor con el IVA y con todas esas cosas para saber cuál fue en teoría, guiño, guiño mi pérdida por haber hecho esa garantía. Ya

**Julián Perdomo:** Vení, vení, Diana, yo tengo una pregunta ahí.

**DIANA:** dale.

**Julián Perdomo:** Eh, vos validaste o vos tenés el flujo claro de cómo se va a hacer el tema de la garantía

**DIANA:** Sí,

**Julián Perdomo:** y la segund y la segunda,

**DIANA:** porque lo estoy haciendo yo.

**Julián Perdomo:** ¿valees ese flujo con con Luis con Edwin y Luis

**DIANA:** Sí. con Edit. Sí,

**Julián Perdomo:** Miguel? ¿Por qué?

**DIANA:** sí.

**Julián Perdomo:** Porque es que yo a ellos les pregunté, de hecho yo el tema de la garantía insistí bastante con ellos en el tema de que no había un estándar y el tema de la garantía, pero ellos siempre me dan una respuesta, por ejemplo, de que ellos manejaban un sistema de outsourcing en donde, por ejemplo, tienen un tercero que es DASA y tienen un mecánico interno no

&nbsp;

&nbsp;

### **01:02:06**

&nbsp;

**DIANA:** Mhm.

**Julián Perdomo:** más. Es decir, ellos no más hacían el ingreso del vehículo y se lo pasaban a DASA. Ellos, qué me decían, hasta donde me acuerdo, ellos me decían que el tema era la garantía, no lo manejaban porque el tercero era el que se hacía responsable de,

**DIANA:** una reunión

**Julián Perdomo:** digamos que de de las garantías,

**DIANA:** de la garantía.

**Julián Perdomo:** si perdía, si ganaban, si Ajá. Entonces, ese tema de la garantía no lo tocamos en las historias de usuario por ese tema.

**DIANA:** Sí,

**Julián Perdomo:** De hecho,

**DIANA:** listo. ¿Qué es lo que pasa?

**Julián Perdomo:** yo yo traté de indagar con ellos, pero no pero en

**DIANA:** Sí, sí, te entiendo. ¿Qué es lo que pasó? De pronto, en ese momento, eh, no hubieron la necesidad de la garantía.

**Julián Perdomo:** Sí,

**DIANA:** ¿Por qué?

**Julián Perdomo:** señora.

**DIANA:** Sí cierto que el vehículo llega y se le pasa al tercero y el tercero es el que me debe

**Julián Perdomo:** Sí,

**DIANA:** responder por la garantía.

**Julián Perdomo:** sí.

**DIANA:** Ya,

**Julián Perdomo:** M.

**DIANA:** Pero de pronto, no sé si recuerdes que muchas veces a ese tercero nosotros le damos algunos insumos, si me entiendes.

&nbsp;

&nbsp;

### **01:03:09**

&nbsp;

**Julián Perdomo:** Sí,

**DIANA:** No sé si recuerdas, por ejemplo, baterías,

**Julián Perdomo:** sí,

**DIANA:** nosotros taller González las compra. Entonces,

**Julián Perdomo:** sí.

**DIANA:** si me llega algo por batería, Dasa me va a decir a mí, que es el tercero, me va a decir,"Venga, pero es que quién me dio esa batería fue usted, ¿quién tiene que cubrir la batería?" Nosotros, a pesar de que fue DASA, nosotros porque la batería, ¿quién fue que la compró? Nosotros. Listo. Por ese lado.

**Julián Perdomo:** Entiendo.

**DIANA:** Segundo, segundo, por más de que Daa, por ejemplo, hizo el cambio de aceite, no sé qué, bla bla,

**Julián Perdomo:** Ajá.

**DIANA:** y él viene porque lo dejaron bajito en aceite, porque se quemó el aceite. Bueno, yo de carros no sé, yo lo enciendo y ando y fin. Ya, pero han venido,

**Julián Perdomo:** Sí.

**DIANA:** ya hemos tenido como tres, no más, tres garantías donde Dasa termina viniéndome a pedir, eh, necesito otros ocho cuartos de aceite, nosotros se los proveemos. Entonces,

**Julián Perdomo:** Sí.

**DIANA:** en teoría yo le debo cobrar esos 8 cuartos a DAS, descontar, porque tú sabes que eso se le descuenta a

&nbsp;

&nbsp;

### **01:04:20**

&nbsp;

**Julián Perdomo:** Ah, sí, porque el responsable el responsable al final sería Dasa y no González el que responda por la garantía.

**DIANA:** Exacto. Entonces, yo se lo tengo que descontar, pero para yo poder saber entró como garantía,

**Julián Perdomo:** Ajá.

**DIANA:** pero el DASA me está viniendo a pedir a mí insumos. Es más que garantía,

**Julián Perdomo:** Sí.

**DIANA:** es para saber que cuando entró por garantías das a saber si me pidió o no me pidió a mí insumos, si me entiendes.

**Julián Perdomo:** Sí,

**DIANA:** Por ejemplo,

**Julián Perdomo:** sí,

**DIANA:** ahorita estamos ahorita estamos en una donde cuando hicimos la orden decía que que cambiaron la correa y la correa fue suministrada por nosotros y inclusive por eso

**Julián Perdomo:** sí.

**DIANA:** la tenía aquí, porque yo la había visto. Eh, eso es policía. La sigla es 27 3803\. Ahí 03\. Esperemos que es esa sí se demore porque como hay tantas órdenes se demora en buscar.

**Julián Perdomo:** en buscar cómo lo está haciendo con un script en ASCP o

**DIANA:** Entonces sí me toca en Java,

**Julián Perdomo:** qué.

**DIANA:** me toca por las extensiones, entonces me toca hacerlo allí.

**Julián Perdomo:** Dale. Y ese formatico que estás construyendo, bueno, ya ya está terminado o apenas está en construcción.

&nbsp;

&nbsp;

### **01:05:41**

&nbsp;

**DIANA:** No, apenas estoy en construcción porque me falta hacerle la validación de los kilómetros,

**Julián Perdomo:** Ah,

**DIANA:** me falta hacerle la validación de los días transcurridos,

**Julián Perdomo:** vale,

**DIANA:** por ende,

**Julián Perdomo:** vale.

**DIANA:** si aplica o no aplica. Falta eh hacer las fórmulas de Ah, venga. Dasa me pidió Dasa me pidió, por ejemplo, 10 galones de aceite, de frenos,

**Julián Perdomo:** Sí.

**DIANA:** de lo que sea. Listo. Estranho. Ah, mira. Y es aquí, aquí viene también lo importante. Este de garantías es también para saber, por ejemplo, de eh cuántas órdenes entró ese vehículo. Mira, este vehículo ha entrado dos veces, uno en el corte dos y otro en el corte 5\.

**Julián Perdomo:** Sí,

**DIANA:** Entonces, la el de la garantía es el corte dos.

**Julián Perdomo:** sí.

**DIANA:** Espérate que cargue porque él está la entero. Mira, yo registro ahorita mira que él dice cambio de correa accesorios. Si yo le doy ver la orden, dice que fue suministrada en las observaciones. Dice que fue suministrada por el taller. El taller lo compró.

**Julián Perdomo:** Sí,

**DIANA:** Listo. Entonces, mira que lo hizo DASA.

&nbsp;

&nbsp;

### **01:06:53**

&nbsp;

**DIANA:** Aquí dice mecánico DASA. Entonces,

**Julián Perdomo:** sí.

**DIANA:** DASA. Dasa va a hacer esto. Puede hacer dos cosas. Me fue para acá. Dasa puede hacer dos cosas en esta garantía. Volverme a pedir a mí taller González. Voy a poner digamos uno y me va a volver a decir,

**Julián Perdomo:** cambiado.

**DIANA:** "Me deme otra correa,

**Julián Perdomo:** Hola,

**DIANA:** deme otra correa de accesorios." Entonces esto es unidad.

**Julián Perdomo:** la correa.

**DIANA:** Póngamosle ahí unidad. Digan, digan que ahí dice unidad. Unidad.

**Julián Perdomo:** Sí.

**DIANA:** Me vuelve y me pide una. Yo debo volver a decirle,"Ay, el señor Dasa me costó 100 pesos. y con el IVA y con no sé qué me quedó en 150\. Ya. Y esto tú sabes que, por ejemplo, Valentina luego va y le dice a al señor Daa,"Ah, venga, como yo le suministré eso de su valor total, yo le tengo que restar estos 150,000 pesos." Ya,

**Julián Perdomo:** Sí.

**DIANA:** en el caso de ahora si fuera Jonathan el que es de aquí y lo hizo Jonathan, el nos toca volver a comprar la correa a nosotros, o sea, el taller González, por más de que diga aquí Jonathan, ah, Taller González tiene que darle la correa a Jonathan, Jonathan la tiene que volver a cambiar.

&nbsp;

&nbsp;

### **01:08:09**

&nbsp;

**DIANA:** Ahora yo no se la voy a descontar a a ni a Jonathan ni a eso, pero sí quién tuvo una pérdida. Taller González. O sea, de las utilidades finales, yo tengo que saber que desconté 150 pesos porque tuvimos que volver a cambiar una correa.

**Julián Perdomo:** Listo. Y en ese caso,

**DIANA:** ¿Listo?

**Julián Perdomo:** bueno, ese formato ya lo tengo más o menos claro. En ese caso,

**DIANA:** H,

**Julián Perdomo:** ¿cuál será el flujo de esa garantía? Es decir, el vehículo ingresa al taller. Me imagino que ese formulario inicial eh

**DIANA:** él llega igual. Él llega igual. Él llega igual, común y corriente. Llega, Brenda lo recibe y entonces el conductor dice,

**Julián Perdomo:** Sí,

**DIANA:** "Ay, yo vengo por garantía." Y ya no ha pasado que vienen por garantía y se aplica.

**Julián Perdomo:** sí.

**DIANA:** Entonces, ah, venga, sí, aplica. Y hay veces no tenemos que suministrarle nada, ni Dasa, ni Jonathan, ni Pedro, nadie tiene que suministrarle nada porque digamos que era un tornillo flojo,

**Julián Perdomo:** Mira. Sí, sí,

**DIANA:** ya nadie perdió.

**Julián Perdomo:** sí.

&nbsp;

&nbsp;

### **01:09:11**

&nbsp;

**DIANA:** Odasa no se lo suministró el taller, sino que Dasa tenía que sí o sí darle porque él compró por allá, digamos, eh un tornillo mal. Ahí el que perdió fue DASA,

**Julián Perdomo:** Sí.

**DIANA:** pero no tengo, o sea, lo que aquí en ese caso sería a modo informativo de que ese vehículo ingresó por garantía y que el señor DASA cumplió la garantía. ¿Listo? ¿Por qué? Porque a futuro si vuelve y viene el vehículo y me dice,"Venga, es que sigue fallando el tornillo." Entonces ya el señor Daa puede decir,"No, qué pena, pero es que yo ya usted le di garantía de eso. Ahora tiene que ingresar como si fuera el vehículo para un diagnóstico y cobrarle eso por aparte." ¿Sí me hago entend?

**Julián Perdomo:** Sí. Sí, sí, esa parte sí,

**DIANA:** Listo.

**Julián Perdomo:** pero en

**DIANA:** Entonces, el vehículo ingresa común y corriente. Brenda le llena el formulario y por allá en las notas observaciones en lo que sea. Brenda dice garantía dentro de las observaciones.

**Julián Perdomo:** Pero un ella ingresa,

**DIANA:** Dime.

**Julián Perdomo:** ella ingresa simplemente el documento de recepción delo.

**DIANA:** Sí. Sí. El azul o el blanco con que tiene la esta de hoja de papel.

&nbsp;

&nbsp;

### **01:10:27**

&nbsp;

**DIANA:** Este sí. Ya. Sí, sí lo ingresa. Como no le podemos cobrar a la entidad, no generamos este control de orden acá no le quedamos la orden.

**Julián Perdomo:** No, sí, sí.

**DIANA:** Lo que vamos a hacer a futuro es crearlas nosotras acá para saber que sí hubo garantía. Ya. Y más por lo que te digo, como está en pruebas, yo las tengo por ahí en las hojas en físico. Por aquí voy a poner, ay, vea. Eh, aquí no lo tengo, pero a futuro. Pues este está en proceso, ¿no? Ah, ¿quién lo hizo? Lo hizo Dasa. Yo podría poner por aquí que ¿Quién lo hizo? Si lo hizo Dasa o lo hizo Jonathan. Ay,

**Julián Perdomo:** Sí.

**DIANA:** lo hizo Dasa. Entonces debo poner por aquí que Dalsa me pidió no sé cuántos cuartos de aceite o la correa o lo que sea y se la debo ir a descontar a o si puede Jonathan pues por allá tengo que ir a hacer mis cálculos y decir que perdí un peso. Listo.

**Julián Perdomo:** Listo.

**DIANA:** Pero este este está en ejecución. ¿Qué es lo que quiero cuando ustedes lo tengan presente? Que ese módulo tiene que existir.

&nbsp;

&nbsp;

### **01:11:46**

&nbsp;

**DIANA:** Entonces,

**Julián Perdomo:** Sí,

**DIANA:** la historia de usuario debe quedar. Esa es de las, digamos, 20 únicas historias de usuario que en este momento no se hacen. Digamos que eh asumiendo nosotros dentro de la metodología,

**Julián Perdomo:** no se pueden.

**DIANA:** esa sería de las últimas a realizar, sabiendo de que este proceso que yo ya lo terminé acá ya queda completamente estandarizado. ¿Listo?

**Julián Perdomo:** Listo, listo, listo,

**DIANA:** Pero la historia debe la historia de usuario debe quedar. Listo,

**Julián Perdomo:** listo, listo, listo. Esa parte la tengo clara,

**DIANA:** listo,

**Julián Perdomo:** la tenemos clara.

**DIANA:** listo, listo. Eh, espérame un segundito. Bueno, entonces, por ejemplo, les estaba diciendo, yo les voy a pasar de dónde venía, de qué documento, para que ustedes se den una idea. Ah, vea,

**Julián Perdomo:** Sí.

**DIANA:** eso fue de asesor jurídico o de gestión de taller. Listo. el contexto y el por qué les estoy haciendo la pregunta y de paso les voy a decir cómo queremos que haga. Entonces, por ejemplo, miren, en este caso le estoy diciendo que es la creada desde la creación de la recepción del vehículo. Vengan, regálenme un minutico, chicos, y ya vengo.

&nbsp;

&nbsp;

### **01:12:59**

&nbsp;

**DIANA:** Listo.

**Julián Perdomo:** Dale,

**DIANA:** Regál, no, cinco. Cinco. Cinco. Ya vengo.

**Julián Perdomo:** dale.

**DIANA:** Listo.

**Julián Perdomo:** Ok. Yeah.

**DIANA:** Listo, chicos. Qué pena. Ya. Entonces, eh estábamos en Me escuchan.

**Julián Perdomo:** Eh, sí, señora, acá estoy.

**DIANA:** Listo, listo, listo. Perfecto. Entonces, eh estamos en la recepción y en la creación del diagnóstico.

**Julián Perdomo:** Sí,

**DIANA:** Dentro de la historia de usuario que vamos a tocar va a ser la de notificar al

**Julián Perdomo:** sí.

**DIANA:** jefe de taller la nueva entrada del vehículo y por ende la

**Julián Perdomo:** Sí,

**DIANA:** creación del diagnóstico del vehículo. ¿Listo?

**Julián Perdomo:** sí, sí, sí, sí.

**DIANA:** Ahora, el contexto dice que en la historia de usuario H5 ya sabemos de cuál, de asesor servicio, el notificar al taller,

**Julián Perdomo:** Sí,

**DIANA:** se indica que el jefe de taller no podrá iniciar diagnósticos hasta que la recepción esté aprobada por la coordinación administrativa.

**Julián Perdomo:** sí. Sí.

**DIANA:** Por otro lado, en la H1 del jefe de taller de diagnóstico establece que el registro del diagnóstico requiere obligatoriamente una orden de trabajo previo y que este diagnóstico requiere

&nbsp;

&nbsp;

### **01:17:25**

&nbsp;

**Julián Perdomo:** Sí.

**DIANA:** aprobación administrativa para diagnosticar el vehículo. Ya eso nos quedó claro. Entonces, acá la pregunta es, ¿solo creo, por ende? El diagnóstico debe ser así. Entonces, dice,"El sistema habilitará obligatoriamente para diagnosticar o la orden. Esta OT es orden, la orden externa, ¿no? La orden externa,

**Julián Perdomo:** La externa externa.

**DIANA:** sí, esta OT es la externa. ¿Listo? Para que me entiendan. Yeah.

**Julián Perdomo:** dice,

**DIANA:** Listo. Voy a de pronto a manejar aunque sea el I o la e para que ustedes sepan. Listo.

**Julián Perdomo:** "Sí, sí, porque nosotros tenemos nosotros tenemos como dos órdenes,

**DIANA:** Está este

**Julián Perdomo:** ¿no? La orden externa,

**DIANA:** sí.

**Julián Perdomo:** que es lo que envía la la entidad y la interna que es la que ustedes hacen por medio de la cotización."

**DIANA:** La la externa. Esta cuando yo digo que esté obligatoriamente es la externa. La interna.

**Julián Perdomo:** Listo.

**DIANA:** Esa sí tiene que existir,

**Julián Perdomo:** Sí.

**DIANA:** que yo lo debo crear y debo crear esa orden, ¿ya? o o decir si se ingresó y quedó dentro de nuestra base de datos y que ingresó la fecha y eso esa orden interna puede ser obligatorio.

&nbsp;

&nbsp;

### **01:18:43**

&nbsp;

**DIANA:** Puede inclusive no es tan necesario porque tengan recuerda Julio que por ejemplo la orden interna ya tiene el diagnóstico.

**Julián Perdomo:** Sí.

**DIANA:** Entonces para generar el diagnóstico de un vehículo que no tiene orden externa no es necesario que tenga orden interna. No es obligatorio, pero lo podríamos manejar así. eh que se haya creado la orden interna. ¿Sí? Entonces, miren que dentro de la respuesta, entonces les voy a poner eso orden trabajo.

**Julián Perdomo:** Pero vení, vení cuando te referías a que la cuando te referís que la orden externa ya viene con un diagnóstico, ¿a qué te referís?

**DIANA:** Mira, ahí dónde tengo una. Dame,

**Julián Perdomo:** Dale,

**DIANA:** dame un segundo.

**Julián Perdomo:** dale.

**DIANA:** Hay algunas entidades,

**Julián Perdomo:** Al.

**DIANA:** no todas, por eso les estoy diciendo que deben deben hacer

**Julián Perdomo:** Ajá.

**DIANA:** esto aquí. Este es policía.

**Julián Perdomo:** Sí,

**DIANA:** Este es el documento que yo te decía que se llama SIGEA. Sigea. Creo que casi no me acuerdo.

**Julián Perdomo:** sí,

**DIANA:** Sigea. Esto es una orden externa, ¿no es cierto?

**Julián Perdomo:** sí.

**DIANA:** Esta orden externa dice, ¿a qué viene?

**Julián Perdomo:** Sí,

**DIANA:** Mantenimiento preventivo y dice que viene al cambio del

&nbsp;

&nbsp;

### **01:19:59**

&nbsp;

**Julián Perdomo:** sí,

**DIANA:** flasher de direccionales, viene al cambio de trompo de freno a los bombillos de los

**Julián Perdomo:** sí,

**DIANA:** direccionales del stock. ¿Por qué?

**Julián Perdomo:** sí,

**DIANA:** Porque ellos allá internamente ellos dijeron,"Eso es lo que queremos que le hagan al carro." Inclusive hay unas que nos aparecen que nos dicen

**Julián Perdomo:** sí.

**DIANA:** eh, va por los cambios de aceite, creo que es esta. Entonces, algunas veces ya trae el diagnóstico y yo no tengo que volver a hacer un diagnóstico. Nosotros lo hacemos para a su vez, porque por ejemplo este, bueno, aquí está y está hacia abajo. Eh, aquí dice tiempo. Ah, este es certificado para una revisión tecnomecánica. Mira que él ya sabe a qué viene. Entonces,

**Julián Perdomo:** Sí.

**DIANA:** yo no tengo que veces realizar ese diagnóstico porque ya lo trae y por acá de tener he de tener otra que me diga que viene por cambio de aceite. No sé si es esta.

**Julián Perdomo:** Pero entonces ese diagnóstico se debe crear sí o sí en el sistema como para tenerlo, ¿no? También o sea solamente

**DIANA:** Sí, ya te voy a decir por qué se debe crear el diagnóstico. Por ejemplo,

**Julián Perdomo:** sí.

**DIANA:** él dice que viene a cambio de aceite y filtros.

&nbsp;

&nbsp;

### **01:21:23**

&nbsp;

**DIANA:** Ya,

**Julián Perdomo:** Sí.

**DIANA:** pero mira que él aquí no me dice qué filtros. El diagnóstico lo hacemos para decir cuántos cuartos de aceite se va a consumir este vehículo, que este vehículo era una tráfic. una Renault Traffic. Ah, esa Renault Traffic se puede consumir 8 cuartos. Entonces, el diagnóstico, recuerda que tú pusiste y esa parte está bien.

**Julián Perdomo:** Sí.

**DIANA:** En el diagnóstico me debe decir las cantidades de los repuestos que voy a hacer. Ah, en este caso el repuesto es un cambio de aceite. Me debe decir cuántos cuartos, litros, galones, como se vaya este eh debe tener. Listo.

**Julián Perdomo:** Sí,

**DIANA:** Aquí solamente me dice filtros, pero por ejemplo eh vamos por aquí,

**Julián Perdomo:** sí, pero eso me imagino que no está traducida la oferta económica.

**DIANA:** aquí, mira. Sí, eso depende de la oferta económica. Entonces, mira que yo sé que digamos esta es una Nissan Frontier. Ah, esta Nissan Frontier dice que le voy a cambiar el filtro del aceite, como es a diésel, el filtro de combustible y el filtro de aire. A pesar de que la orden ya viene, entonces sí debo hacerle el diagnóstico para saber

**Julián Perdomo:** Sí.

**DIANA:** qué o cuántos eh cuartos voy a tener.

&nbsp;

&nbsp;

### **01:22:45**

&nbsp;

**DIANA:** Pero si él me viene sin esta orden y sea esto, ahí sí hago la orden interna y digo

**Julián Perdomo:** Sí,

**DIANA:** vehículo que ingresó.

**Julián Perdomo:** sí.

**DIANA:** pasar a pasar a realizar diagnóstico para que me diga el jefe de taller me diga,"Vea, es que viene para que le cambien las pastillas de los frenos, el líquido de frenos, la batería." Ah, ya. Y ahí sí yo como ya tengo mi orden interna porque ya lo había registrado con esa orden interna yo creo guiño guiño este porque el objetivo es este. Ay venga, le vamos a cambiar el aceite de motor y se va a gastar 7 cuart. Le voy a cambiar un filtro, le voy a cambiar una batería, le voy a cambiar una correa de accesorios.

**Julián Perdomo:** Sí.

**DIANA:** Listo. Eh, por eso también es el diagnóstico.

**Julián Perdomo:** Sí.

**DIANA:** Ya. Sí. Entonces, en este documento que estábamos mirando acá, esta orden externa que estábamos diciendo aquí, ustedes pusieron que no se podrá iniciar el diagnóstico hasta que la recepción apruebe bla bla bla.

**Julián Perdomo:** Sí.

**DIANA:** Ah. Aquí dice, y aquí dice que el registro de un diagnóstico requiere obligatoriamente una orden de trabajo.

**Julián Perdomo:** Sí.

**DIANA:** Entonces, mira que volvemos a lo mismo que tú me preguntaste y por eso yo te dije OT es orden de trabajo externa, pero si lo arreglan, ¿cómo lo arreglan?

&nbsp;

&nbsp;

### **01:24:24**

&nbsp;

**DIANA:** Orden de no externa, sino interna. y le ponen OTI.

**Julián Perdomo:** Ah,

**DIANA:** ¿Cuál es la única?

**Julián Perdomo:** lo dejamos. Sí,

**DIANA:** La interna es la obligatoria.

**Julián Perdomo:** es que lo dejamos muy en vivo.

**DIANA:** Exacto. Y en las historias de usuario no me puedes dejar nada ambiguo.

**Julián Perdomo:** Listo.

**DIANA:** Por eso les estoy mandando estas correcciones y les estoy diciendo cómo me deben decir las cosas. Por eso aquí en la respuesta yo que iba a poner la orden externa no es necesaria. Ya lo dijimos desde la anterior vez, ¿no? Es obligatoria.

**Julián Perdomo:** Mhm.

**DIANA:** Obligatoria. La que es obligatoria es la orden de trabajo interna, la que creamos nosotras acá. Esa es la que la que me dice en qué consecutivo voy. La que me dice aquí eh a qué corte pertenece. Eh, sí, la fecha en que ingresó. Listo. Listo. Esa es la respuesta. Listo. Orden externa no es obligatoria. La interna es obligatoria. ¿Listo? Voy a dejarlo como estado original para que ustedes y evitemos esas ambigüedades. Entonces, si ya la si ya entendiste que no me puedes hacer ambigüedades, en muchos de los documentos está pasando eso.

&nbsp;

&nbsp;

### **01:25:57**

&nbsp;

**DIANA:** No sabemos a qué tipo de orden se están refiriendo, a la interna o a la externa. Y tenemos que aclarar esas cosas.

**Julián Perdomo:** Là Listo.

**DIANA:** ¿Listo? Eh, aquí por ejemplo dice que es también la creación del diagnóstico. Eh, tará, el diagnóstico especifica que el jefe de taller podrá registrar hallazgos mediante notas de voz, las cuales serán transcritas y adjuntas al diagnóstico para ser consultadas a través del servicio. Aquí viene la pregunta. Ya. El sistema puede conservar y permitir reproducir el audio grabado o el audio únicamente se utiliza como un insumo temporal para la transcripción de la orden. Aquí volvemos a lo que ya te mencioné. ¿Qué orden, interna o externa? Para mí tendría que ser la interna, ¿no es cierto?

**Julián Perdomo:** interna la interna en Sí.

**DIANA:** Listo. Listo. ¿Qué es lo que pasa? Así como tenemos el documento, tú te acuerdas que tenemos el documento de la orden, eh el papelito que Juan Diego escribe, qué es lo que se le va a hacer y nosotros los archivamos porque necesitamos una trazabilidad. Lo mismo debe pasar con estos mensajes de voz. Se deben guardar en dónde, en alguna parte. Ya yo no los puedo dejar de manera temporal. Y esas son las cosas que deben quedar escritas dentro de la historia de usuario.

&nbsp;

&nbsp;

### **01:27:26**

&nbsp;

**DIANA:** Debe dentro del criterio de aceptación, el documento, la voz, el no sé qué, como me haya mandado él, ese debe quedar guardado porque es que va a ser el soporte de decir el jefe de taller me pidió dos llantas, me pidió cinco filtros.

**Julián Perdomo:** Mhm.

**DIANA:** Listo. Entonces se debe guardar y hacia quién está, o sea, hacia quién está afiliado o hacia quién va dirigida esa orden. Y eso dijimos que es para la orden interna. Ya. Entonces, para que me lo especifiques, se puede descartar al cuánto tiempo. Ya. Esto, por ejemplo, me me tocaría preguntárselo, por ejemplo, bien a ellos, pero para mí para mí él debe guardarse mínimo, mínimo, por ejemplo, eh se debe guardar por un periodo de tiempo. Periodo de tiempo. el corte ya se terminó, es decir, que yo ya o el contrato ya se terminó, entonces yo voy a decir un periodo de tiempo de ejemplo 6 meses de después de la finalización del contrato. ¿Por qué? Volvemos a lo mismo, si ellos vienen por garantía, yo les puedo decir,"Vad, es que el jefe de taller dijo esto y esto y esto y esto y si se le cambió esto y esto y esto." Ya esta parte del periodo aún por no se las voy a poner porque no la tengo validada con con don y con Luis Miguel, pero entonces se las voy confirmando.

&nbsp;

&nbsp;

### **01:29:11**

&nbsp;

**DIANA:** ¿Listo?

**Julián Perdomo:** Listo.

**DIANA:** Ahora,

**Julián Perdomo:** Eh,

**DIANA:** pero les voy haciendo para que ustedes tengan presente.

**Julián Perdomo:** Diana,

**DIANA:** Dime.

**Julián Perdomo:** Diana, te comentamos que ya lo que es Julio y yo, yo, por ejemplo, tengo que entrar una reunión, Julio tiene que proceder con los trabajos que tiene la universidad. ¿Qué te parece si concluimos la sesión hoy aquí? Ya nosotros tenemos grabación,

**DIANA:** Dale.

**Julián Perdomo:** transcripción y y ver si nos podemos reunir. Mañana podríamos agendar otra hora. Sí, mañana podríamos a qué horas podríamos agendar,

**DIANA:** Sí. Perfecto.

**Julián Perdomo:** Diana.

**DIANA:** Hagámoslo en la tarde igual para que ustedes alcancen a hacer los ajustes que les dije sobre la historia de usuario que ya estaban para que le queden bien las historias de usuario, podérselas revisar y así sepan cómo es que queremos que queden y así prosigamos con estos nuevos ajustes que estoy aquí trabajando. No. Listo.

**Julián Perdomo:** Listo. Vale, entonces igualmente a las 3\.

**DIANA:** Listo. Entonces, en la tarde.

**Julián Perdomo:** ¿Te parece bien?

**DIANA:** Sí, perfecto.

**Julián Perdomo:** Listo,

**DIANA:** A las 3 me parece perfecto.

**Julián Perdomo:** listo. Diana, Diana, te agradecemos mucho por el espacio, por la retroalimentación. Nosotros vamos a estar revisando el documento igualmente. Ese contexto y dudas agradecemos los para ir compartiendo.

**DIANA:** Listo. Sí, yo te lo comparto, pero entonces déjame termino y certifico otras cosas y cuando ya lo tenga completamente

**Julián Perdomo:** Ah, vale,

**DIANA:** y se los termine de socializar te lo comparto para que no este por el momento

**Julián Perdomo:** listo.

**DIANA:** focalízate en el cambio de la historia de usuario que es ya fue entregado, que ya fue socializado. Listo,

**Julián Perdomo:** Ah, okay. Listo. Vale.

**DIANA:** listo,

**Julián Perdomo:** Perfecto.

**DIANA:** listo.

**Julián Perdomo:** Listo,

**DIANA:** Bueno,

**Julián Perdomo:** listo.

**DIANA:** bueno, vale. Chao. Gracias.

**Julián Perdomo:** Chao. Eh, ten la grabación aquí, ¿no? Ajá. Tá.

&nbsp;

&nbsp;

### **La transcripción finalizó después de 01:31:03**

&nbsp;

*Esta transcripción editable se generó por computadora y puede contener errores. Los usuarios también pueden cambiar el texto después de que se cree.*