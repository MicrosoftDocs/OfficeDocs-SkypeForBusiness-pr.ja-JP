---
title: LyncPerfTool を実行する
description: LyncPerfTool を実行します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3278754c9154f47602c5c4f1fa95cdc4b465b228
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560083"
---
# <a name="run-lyncperftool"></a><span data-ttu-id="289ca-103">LyncPerfTool を実行する</span><span class="sxs-lookup"><span data-stu-id="289ca-103">Run LyncPerfTool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="289ca-104">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="289ca-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="289ca-105">Lync Server 2013 ストレスおよびパフォーマンスツール (LyncPerfTool.exe) を実行する前に、ユーザー、連絡先、およびシナリオを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="289ca-105">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="289ca-106">これらの操作を実行するためのツールの使用の詳細については、「 [Create Users And Contacts](create-users-and-contacts.md) 」および「 [Configure User Profile](configure-user-profile.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="289ca-106">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="289ca-107">これらのツールを実行すると、必要なパラメーターが含まれるバッチファイルの一部として LyncPerfTool.exe を実行するファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="289ca-107">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="289ca-108">Lync Server 2013 ストレスおよびパフォーマンスツールの実行</span><span class="sxs-lookup"><span data-stu-id="289ca-108">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="289ca-109">UserProfileGenerator.exe ツールは、LyncPerfTool パフォーマンスカウンターを登録し、XML 構成ファイルを読み込むことによって LyncPerfTool.exe を実行できるバッチファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="289ca-109">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="289ca-110">バッチファイルでは、構成ファイルごとに LyncPerfTool.exe の1つのインスタンスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="289ca-110">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="289ca-111">バッチファイルを実行するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="289ca-111">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="289ca-112">構成フォルダーとファイルが格納されているフォルダーを、各クライアントコンピューター上の LyncStressTool.exe が格納されているディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="289ca-112">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="289ca-113">(たとえば、1.28 13.16.16 という名前のフォルダーに構成ファイルを生成した場合は、 \_ そのフォルダーを各クライアント上の LyncPerfTool.exe を含むフォルダーにコピーします。)</span><span class="sxs-lookup"><span data-stu-id="289ca-113">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="289ca-114">適切な番号が付けられたクライアントフォルダーに移動し、RunClient バッチスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="289ca-114">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="289ca-115">Windows Explorer でバッチファイルをダブルクリックするだけで、そのクライアント番号のすべての構成ファイルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="289ca-115">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="289ca-116">また、次の構文を使用して、適切なクライアントフォルダーからスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="289ca-116">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="289ca-117">LyncPerfTool.exe を直接実行するには、コマンドプロンプトを開き、コマンドラインで次のコマンドを入力します (この操作を初めて実行するときは、このトピックで後述する「メモ」に示すように、パフォーマンスカウンター regsvr32/i/n/s LyncPerfToolPerf.dll を登録してください) :LyncPerfTool.exe/クリックします。\<configXML\></span><span class="sxs-lookup"><span data-stu-id="289ca-117">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="289ca-118">構成ファイルの値をツールに表示するには、次のように、上記のコマンドに、次のようにして、/displayfile パラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="289ca-118">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="289ca-119">プロセスを終了するには、Ctrl + C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="289ca-119">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="289ca-120">LyncPerfTool を直接実行する前に、パフォーマンスカウンターを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="289ca-120">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="289ca-121">次のコマンドを入力して、パフォーマンスカウンターを登録します。</span><span class="sxs-lookup"><span data-stu-id="289ca-121">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="289ca-122">開始する LyncPerfTool.exe のすべてのインスタンスは、通常、1秒あたり1ユーザーの割合でユーザーによるサインインを直ちに開始します。</span><span class="sxs-lookup"><span data-stu-id="289ca-122">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="289ca-123">プールのピークユーザーのサインイン率は約 12/秒です。</span><span class="sxs-lookup"><span data-stu-id="289ca-123">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="289ca-124">これは、ユーザーがまだサインインしている間、12個を超える LyncPerfTool インスタンスを同時に開始してはならないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="289ca-124">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="289ca-125">1000ユーザーが完全にサインインするには、1秒あたり約20分かかります。</span><span class="sxs-lookup"><span data-stu-id="289ca-125">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="289ca-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="289ca-126">See Also</span></span>


[<span data-ttu-id="289ca-127">ユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="289ca-127">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="289ca-128">ユーザープロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="289ca-128">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

