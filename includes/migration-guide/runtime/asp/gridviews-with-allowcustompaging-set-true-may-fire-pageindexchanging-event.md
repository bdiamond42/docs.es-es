### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a><span data-ttu-id="a1024-101">GridView con AllowCustomPaging establecido en true puede desencadenar el evento PageIndexChanging al salir de la última página de la vista</span><span class="sxs-lookup"><span data-stu-id="a1024-101">GridViews with AllowCustomPaging set to true may fire the PageIndexChanging event when leaving the final page of the view</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a1024-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a1024-102">Details</span></span>|<span data-ttu-id="a1024-103">Un error en .NET Framework 4.5 hace que en ocasiones no se desencadene <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=name> para los elementos <xref:System.Web.UI.WebControls.GridView?displayProperty=name> en los que se ha habilitado <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="a1024-103">A bug in the .NET Framework 4.5 causes <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=name> to sometimes not fire for <xref:System.Web.UI.WebControls.GridView?displayProperty=name>s that have enabled <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=name>.</span></span>|
|<span data-ttu-id="a1024-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a1024-104">Suggestion</span></span>|<span data-ttu-id="a1024-105">Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a1024-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span> <span data-ttu-id="a1024-106">Como una solución alternativa, la aplicación puede realizar una BindGrid explícita en cualquier método <code>Page_Load</code> que cumpla estas condiciones (la <xref:System.Web.UI.WebControls.GridView?displayProperty=name> está en la última página y Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=name> es diferente de <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=name>).</span><span class="sxs-lookup"><span data-stu-id="a1024-106">As a work-around, the app can do an explicit BindGrid on any <code>Page_Load</code> that would hit these conditions (the <xref:System.Web.UI.WebControls.GridView?displayProperty=name> is on the last page and Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=name> is different from <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=name>).</span></span> <span data-ttu-id="a1024-107">Como alternativa, la aplicación se puede modificar para permitir la paginación (en lugar de la paginación personalizada), dado que ese escenario no ilustra el problema.</span><span class="sxs-lookup"><span data-stu-id="a1024-107">Alternatively, the app can be modified to allow paging (instead of custom paging), as that scenario does not demonstrate the problem.</span></span>|
|<span data-ttu-id="a1024-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a1024-108">Scope</span></span>|<span data-ttu-id="a1024-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="a1024-109">Minor</span></span>|
|<span data-ttu-id="a1024-110">Versión</span><span class="sxs-lookup"><span data-stu-id="a1024-110">Version</span></span>|<span data-ttu-id="a1024-111">4.5</span><span class="sxs-lookup"><span data-stu-id="a1024-111">4.5</span></span>|
|<span data-ttu-id="a1024-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="a1024-112">Type</span></span>|<span data-ttu-id="a1024-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a1024-113">Runtime</span></span>|
|<span data-ttu-id="a1024-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a1024-114">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|
