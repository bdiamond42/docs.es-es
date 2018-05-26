### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a><span data-ttu-id="bd6a1-101">Cambio de comportamiento para los métodos Task.WaitAll con argumentos de tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="bd6a1-101">Change in behavior for Task.WaitAll methods with time-out arguments</span></span>

|   |   |
|---|---|
|<span data-ttu-id="bd6a1-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="bd6a1-102">Details</span></span>|<span data-ttu-id="bd6a1-103">El comportamiento de <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> se ha hecho más coherente en .NET Framework 4.5. En .NET Framework 4, estos métodos se comportaban de forma incoherente.</span><span class="sxs-lookup"><span data-stu-id="bd6a1-103"><xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> behavior was made more consistent in .NET Framework 4.5.In the .NET Framework 4, these methods behaved inconsistently.</span></span> <span data-ttu-id="bd6a1-104">Cuando se agotaba el tiempo de espera, si una o varias tareas se completaban o cancelaban antes de la llamada al método, el método producía una excepción <xref:System.AggregateException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="bd6a1-104">When the time-out expired, if one or more tasks were completed or canceled before the method call, the method threw an <xref:System.AggregateException?displayProperty=name> exception.</span></span> <span data-ttu-id="bd6a1-105">Cuando se agotaba el tiempo de espera, si no se completaba ni cancelaba ninguna tarea antes de la llamada al método, pero una o varias tareas entraban en estos estados después de la llamada al método, el método pasaba a ser false.</span><span class="sxs-lookup"><span data-stu-id="bd6a1-105">When the time-out expired, if no tasks were completed or canceled before the method call, but one or more tasks entered these states after the method call, the method returned false.</span></span><br/><br/><span data-ttu-id="bd6a1-106">En .NET Framework 4.5, estas sobrecargas de método ahora devuelven false si las tareas siguen en ejecución cuando se agota el intervalo de tiempo de espera e inician una excepción <xref:System.AggregateException?displayProperty=name> solo si se ha cancelado una tarea de entrada (con independencia de si se canceló antes o después de la llamada al método) y no hay otras tareas en ejecución.</span><span class="sxs-lookup"><span data-stu-id="bd6a1-106">In the .NET Framework 4.5, these method overloads now return false if any tasks are still running when the time-out interval expired, and they throw an <xref:System.AggregateException?displayProperty=name> exception only if an input task was cancelled (regardless of whether it was before or after the method call) and no other tasks are still running.</span></span>|
|<span data-ttu-id="bd6a1-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="bd6a1-107">Suggestion</span></span>|<span data-ttu-id="bd6a1-108">Si se detectó una excepción <xref:System.AggregateException?displayProperty=name> como medio de detección de una tarea que se canceló antes de invocar la llamada a <xref:System.Threading.Tasks.Task.WaitAll%2A>, es necesario que ese código realice la misma detección mediante la propiedad <xref:System.Threading.Tasks.Task.IsCanceled%2A> (por ejemplo, .Any(t =&gt; t.IsCanceled)), ya que .NET Framework 4.6 solo iniciará una excepción en ese caso si todas las tareas esperadas se completan antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="bd6a1-108">If an <xref:System.AggregateException?displayProperty=name> was being caught as a means of detecting a task that was cancelled prior to the <xref:System.Threading.Tasks.Task.WaitAll%2A> call being invoked, that code should instead do the same detection via the  <xref:System.Threading.Tasks.Task.IsCanceled%2A> property (for example: .Any(t =&gt; t.IsCanceled)) since .NET Framework 4.6 will only throw in that case if all awaited tasks are completed prior to the timeout.</span></span>|
|<span data-ttu-id="bd6a1-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="bd6a1-109">Scope</span></span>|<span data-ttu-id="bd6a1-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="bd6a1-110">Minor</span></span>|
|<span data-ttu-id="bd6a1-111">Versión</span><span class="sxs-lookup"><span data-stu-id="bd6a1-111">Version</span></span>|<span data-ttu-id="bd6a1-112">4.5</span><span class="sxs-lookup"><span data-stu-id="bd6a1-112">4.5</span></span>|
|<span data-ttu-id="bd6a1-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="bd6a1-113">Type</span></span>|<span data-ttu-id="bd6a1-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="bd6a1-114">Runtime</span></span>|
|<span data-ttu-id="bd6a1-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="bd6a1-115">Affected APIs</span></span>|<ul><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType></li></ul>|
