---
title: Skype for Business Online コマンドレットと他の Windows PowerShell コマンドレットの組み合わせ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7455ba7d98ecc11fcfc6e0c255eb430e213d3f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42000752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="24b4c-102">Skype for Business Online コマンドレットと他の Windows PowerShell コマンドレットの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="24b4c-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24b4c-103">_**トピックの最終更新日:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="24b4c-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="24b4c-104">Windows PowerShell を使用して Skype for Business Online に接続すると、約40の Skype for Business Online コマンドレットを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="24b4c-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="24b4c-105">ただし、Skype for Business Online を管理する場合は、これらの40コマンドレットのみを使用することに制限はありません。</span><span class="sxs-lookup"><span data-stu-id="24b4c-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="24b4c-106">Skype for Business Online のコマンドレットに加えて、コンピューターにインストールされている他の Windows PowerShell コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="24b4c-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="24b4c-107">(Windows PowerShell 3.0 をインストールすると、数百種類の Windows PowerShell コマンドレットもインストールされます。)コマンドでは、Skype for Business Online コマンドレットと、コンピューターで使用可能なその他のコマンドレットを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="24b4c-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="24b4c-108">Windows PowerShell 3.0 の完全なコースはこの記事の範囲を超えていますが、コマンドレットを組み合わせて使用する必要がある理由を示すいくつかの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="24b4c-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="24b4c-109">最初に、Skype for Business Online コマンドレットには印刷コマンドは含まれていません。また、Windows PowerShell コンソールでこのコマンドは見つかりません。</span><span class="sxs-lookup"><span data-stu-id="24b4c-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="24b4c-110">では、コマンドレットによって取得された情報の印刷結果を取得するにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="24b4c-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="24b4c-111">1つの方法として、情報を取得し、その情報を**プリンター**コマンドレットに送信する方法があります。</span><span class="sxs-lookup"><span data-stu-id="24b4c-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="24b4c-112">追加のパラメーターは含まれていないため、**出力**コマンドレットによって返されるすべての情報が既定のプリンターに出力されます。</span><span class="sxs-lookup"><span data-stu-id="24b4c-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="24b4c-113">同様に、Skype for Business Online のコマンドレットには、データをファイルに保存するためのパラメーターが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="24b4c-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="24b4c-114">しかし、このコマンドは次の**コマンドレットを使用して**、返された情報をテキストファイル C:\\Logs\\output.txt に保存します。</span><span class="sxs-lookup"><span data-stu-id="24b4c-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="24b4c-115">このコマンドは、**オブジェクトの選択**コマンドレットを使用して、返され、画面に表示されるデータを制限します。</span><span class="sxs-lookup"><span data-stu-id="24b4c-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="24b4c-116">この例[では、](https://technet.microsoft.com/library/JJ994026(v=OCS.15))すべての Skype For business Online ユーザーの情報を取得し、次に**オブジェクトの選択**コマンドレットを使用して、表示されるデータをユーザーの id 値とそのアーカイブポリシーに制限します。</span><span class="sxs-lookup"><span data-stu-id="24b4c-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="24b4c-117">コンピューター上で使用できるコマンドレットが数百あるため、Skype for Business Online コマンドレットとなっているコマンドレットを判別するのは困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="24b4c-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="24b4c-118">Skype for Business Online コマンドレット (および Skype for Business Online コマンドレットのみ) の一覧を取得するには、まず、すべての Skype for Business Online コマンドレットを含む Windows PowerShell の一時モジュールの名前を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24b4c-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="24b4c-119">そのために、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="24b4c-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="24b4c-120">次のような情報が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="24b4c-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="24b4c-121">ModuleType スクリプトを持つモジュールは、Skype for Business Online のコマンドレットを含むモジュールです。</span><span class="sxs-lookup"><span data-stu-id="24b4c-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="24b4c-122">これらのコマンドレットの一覧を取得するには、モジュール名としてスクリプトモジュールの名前を使用して、**コマンド**レットを実行します。</span><span class="sxs-lookup"><span data-stu-id="24b4c-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="24b4c-123">ModuleType がスクリプトと等しい複数のモジュールを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="24b4c-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="24b4c-124">その場合は、次のコマンドを実行して、 **get-cstenant**コマンドレットが含まれているモジュールを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="24b4c-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="24b4c-125">**Get-cstenant**コマンドレットに対して返されるモジュールは、すべての Skype For business Online コマンドレットを含むモジュールになります。</span><span class="sxs-lookup"><span data-stu-id="24b4c-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="24b4c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="24b4c-126">See Also</span></span>


<span data-ttu-id="24b4c-127">[Windows PowerShell と Skype for Business Online の概要](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="24b4c-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

