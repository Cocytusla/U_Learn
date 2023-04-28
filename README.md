# U_Learn


观察者模式是一种设计模式，其思想是定义对象之间的一种一对多的依赖关系，让多个观察者对象同时监听某一个主题对象，当这个主题对象发生变化时，它的所有依赖者（观察者）都会收到通知并自动更新。

在观察者模式中，主题对象通常包含一个观察者列表，可以动态地增加或删除观察者对象。而观察者对象则通常定义一个接口，用于接收主题对象的通知并进行相关的处理。

观察者模式的优点是降低了主题对象和观察者对象之间的耦合度，使得它们可以独立地变化和扩展。同时，它也提供了一种灵活的设计方式，可以方便地实现事件驱动的编程模型。

观察者模式在实际应用中广泛使用，例如GUI界面中的事件处理、消息通知系统等。

ChatGPT
ChatGPT

在Unity中，OnCollisionEnter是一个用于检测碰撞事件的函数，它会在物体与其他物体发生碰撞时被调用。该函数必须定义在继承自MonoBehaviour的脚本类中，并且参数是一个Collision类型的对象，用于描述发生碰撞的详细信息。

OnCollisionEnter函数的语法如下：

csharp
Copy
void OnCollisionEnter(Collision collision)
{
    // 处理碰撞事件
}
在碰撞事件发生时，Unity会自动调用OnCollisionEnter函数，并将碰撞事件的详细信息存储在collision参数中。我们可以使用collision参数来获取碰撞事件的相关信息，例如碰撞发生的位置、碰撞物体的属性、碰撞的力等等。

例如，如果要在物体发生碰撞时输出一条调试信息，则可以使用以下代码：

csharp
Copy
void OnCollisionEnter(Collision collision)
{
    Debug.Log("碰撞发生在：" + collision.contacts[0].point);
}
在这个示例中，我们使用OnCollisionEnter函数检测碰撞事件，并在控制台输出碰撞发生的位置。

需要注意的是，OnCollisionEnter函数只会在物体的碰撞器与其他物体的碰撞器发生实际碰撞时被调用，而不是当它们接触时就被调用。此外，OnCollisionEnter函数只会在物体有刚体组件时被调用。如果物体没有刚体组件，则应该使用OnTriggerEnter函数来检测触发器事件。

函数重载

函数重载（Function Overloading）是指在同一个作用域内，定义多个同名的函数，但这些函数的参数列表不同（参数类型、参数个数或参数顺序不同）。

在函数重载中，当调用函数时，编译器会根据传入的参数类型、个数和顺序来自动选择合适的函数进行调用。这样可以提高代码的灵活性和可读性，使代码更加简洁和易于维护。

函数重载的语法如下：

csharp
Copy
// 函数定义
void FunctionName(int arg1);
void FunctionName(float arg1);
void FunctionName(int arg1, float arg2);

// 函数调用
FunctionName(5); // 调用第一个函数
FunctionName(3.14f); // 调用第二个函数
FunctionName(10, 3.14f); // 调用第三个函数
在这个示例中，我们定义了三个同名的函数FunctionName，分别接受一个整型参数、一个浮点型参数和一个整型参数和一个浮点型参数。在调用函数时，编译器会根据传入的参数类型和个数来选择合适的函数进行调用。

需要注意的是，函数重载的参数列表必须不同，不能只是在参数名称或默认参数上有所区别。此外，函数返回值不参与函数重载的判断，因此不能通过返回值的不同来进行函数重载。

Vector3.sqrMagnitude

在Unity中，Vector3.sqrMagnitude是一个用于计算向量长度平方的函数。它可以用于优化代码性能，因为它比计算向量长度更快，而且不需要执行平方根运算，可以节约一部分计算时间。

Vector3.sqrMagnitude函数的语法如下：

csharp
Copy
public float sqrMagnitude { get; }
该函数不需要参数，直接返回Vector3向量的长度平方。向量长度平方是向量的X、Y和Z分量的平方和，计算公式如下：

sqrMagnitude = xx + yy + z*z

例如，如果要计算两个向量之间的距离平方，则可以使用以下代码：

csharp
Copy
Vector3 v1 = new Vector3(1, 2, 3);
Vector3 v2 = new Vector3(4, 5, 6);
float distanceSqr = (v1 - v2).sqrMagnitude;
在这个示例中，我们定义了两个向量v1和v2，然后计算它们之间的距离平方。我们首先计算两个向量的差向量，然后调用sqrMagnitude函数计算其长度平方，并将结果存储在distanceSqr变量中。

需要注意的是，Vector3.magnitude函数计算向量的实际长度，而Vector3.sqrMagnitude函数只计算向量长度的平方。因此，在需要精确计算向量长度时应该使用magnitude函数，而在需要优化代码性能时可以使用sqrMagnitude函数。

velocity

在物理引擎中，velocity指的是物体的速度向量，它表示物体每秒移动的距离和方向。在Unity中，velocity通常用于描述刚体的运动状态，可以通过Rigidbody组件的velocity属性来获取或设置物体的速度向量。

velocity属性的类型是Vector3，它表示物体在三个坐标轴上的速度分量。例如，如果一个物体的velocity属性为(0, 2, 0)，则表示它在Y轴上以每秒2个单位的速度向上移动。

可以通过以下代码来获取或设置物体的速度向量：

csharp
Copy
// 获取物体的速度向量
Vector3 velocity = GetComponent<Rigidbody>().velocity;

// 设置物体的速度向量
GetComponent<Rigidbody>().velocity = new Vector3(1, 0, 0);
在这个示例中，我们首先使用GetComponent函数获取物体的Rigidbody组件，然后通过velocity属性来获取或设置物体的速度向量。

需要注意的是，velocity属性只能用于描述物体的线性速度，而不能描述物体的旋转速度。对于旋转速度，需要使用Rigidbody组件的angularVelocity属性。此外，物体的速度是受到物理引擎模拟的，因此需要将物体的刚体类型设置为Dynamic或Kinematic才能使用velocity属性。

Particle System

在Unity中，Particle System（粒子系统）是用于创建和渲染大量粒子效果的组件。它可以用于创建火花、爆炸、烟雾、雨、雪等特效。使用Particle System可以让游戏场景更加真实和生动。

Particle System组件可以通过菜单栏的GameObject -> Effects -> Particle System来创建，也可以通过代码动态创建。创建完成后，可以在Inspector面板中调整各种粒子效果的属性，例如粒子的数量、速度、生命周期、颜色、大小、形状等。

下面是一些常用的Particle System属性：

Duration：粒子系统的持续时间。
Start Lifetime：粒子的生命周期。
Start Speed：粒子的初始速度。
Start Size：粒子的初始大小。
Start Color：粒子的初始颜色。
Shape：粒子的发射形状，例如球体、圆锥体、平面等。
Emission：粒子的发射率和范围。
Renderer：粒子的渲染器，可以选择使用Mesh或Billboard方式进行渲染。
除了调整属性外，还可以通过代码来控制Particle System的播放、停止、暂停、重置等操作，例如：

csharp
Copy
// 获取Particle System组件
ParticleSystem particleSystem = GetComponent<ParticleSystem>();

// 播放粒子效果
particleSystem.Play();

// 停止粒子效果
particleSystem.Stop();
在这个示例中，我们首先使用GetComponent函数获取物体上的Particle System组件，然后通过Play和Stop方法来控制粒子效果的播放和停止。

需要注意的是，Particle System是一个比较耗费性能的组件，因此在使用时需要注意性能优化，例如减少粒子数量、降低粒子质量、使用LOD等方式来提高性能。

Instantiate

在Unity中，Instantiate是一个用于创建新的游戏对象实例的函数。它可以用于在运行时动态地创建游戏对象，例如在游戏中生成敌人、子弹、道具等。

Instantiate函数的语法如下：

csharp
Copy
public static Object Instantiate(Object original);
public static Object Instantiate(Object original, Vector3 position, Quaternion rotation);
第一个函数重载的参数是要创建的游戏对象的原型，即原始的Prefab或其他GameObject。该函数会返回一个Object类型的实例，我们需要将其转换为GameObject或其他类型，例如：

csharp
Copy
GameObject prefab = Resources.Load<GameObject>("PrefabName");
GameObject instance = Instantiate(prefab);
在这个示例中，我们首先使用Resources.Load函数加载一个名为PrefabName的Prefab资源，然后使用Instantiate函数创建一个新的游戏对象实例。最后，我们将返回的Object类型实例转换为GameObject类型，并将其存储在instance变量中。

第二个函数重载的参数除了原型之外，还包括要创建的游戏对象的初始位置和旋转角度。例如：

csharp
Copy
GameObject prefab = Resources.Load<GameObject>("PrefabName");
GameObject instance = Instantiate(prefab, new Vector3(0, 0, 0), Quaternion.identity);
在这个示例中，我们通过传递一个新的Vector3位置和一个空的Quaternion旋转角度来创建一个新的游戏对象实例。

需要注意的是，Instantiate函数创建的游戏对象实例是在场景中动态创建的，因此需要在适当的时候销毁它们，以避免内存泄漏和性能问题。可以使用Destroy函数来销毁不再需要的游戏对象实例，例如：

csharp
Copy
Destroy(instance);
在这个示例中，我们使用Destroy函数销毁了之前创建的游戏对象实例。
