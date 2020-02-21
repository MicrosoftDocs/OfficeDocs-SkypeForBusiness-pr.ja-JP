---
title: LyncPerfTool を実行する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4c7d7de6dcb2f2eee15e7da0809dd6e3c41e07
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a><span data-ttu-id="2576b-102">LyncPerfTool を実行する</span><span class="sxs-lookup"><span data-stu-id="2576b-102">Run LyncPerfTool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2576b-103">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="2576b-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="2576b-104">Lync Server 2013 ストレスおよびパフォーマンスツール (LyncPerfTool) を実行する前に、ユーザー、連絡先、およびシナリオを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2576b-104">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="2576b-105">これらの操作を実行するためのツールの使用の詳細については、「 [Create Users And Contacts](create-users-and-contacts.md) 」および「 [Configure User Profile](configure-user-profile.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2576b-105">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="2576b-106">これらのツールを実行すると、必要なパラメーターが含まれるバッチファイルの一部として LyncPerfTool を実行するファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="2576b-106">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="2576b-107">Lync Server 2013 ストレスおよびパフォーマンスツールの実行</span><span class="sxs-lookup"><span data-stu-id="2576b-107">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="2576b-108">Userprofilegenerator.exe ツールは、LyncPerfTool パフォーマンスカウンターを登録し、XML 構成ファイルを読み込むことによって LyncPerfTool を実行できるバッチファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2576b-108">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="2576b-109">バッチファイルでは、構成ファイルごとに LyncPerfTool の1つのインスタンスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="2576b-109">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="2576b-110">バッチファイルを実行するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2576b-110">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="2576b-111">構成フォルダーとファイルが格納されているフォルダーを、各クライアントコンピューター上の LyncStressTool が格納されているディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="2576b-111">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="2576b-112">(たとえば、1.28\_13.16.16 という名前のフォルダーに構成ファイルを生成した場合、そのフォルダーを各クライアント上の LyncPerfTool を含むフォルダーにコピーします。)</span><span class="sxs-lookup"><span data-stu-id="2576b-112">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="2576b-113">適切な番号が付けられたクライアントフォルダーに移動し、RunClient バッチスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="2576b-113">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="2576b-114">Windows Explorer でバッチファイルをダブルクリックするだけで、そのクライアント番号のすべての構成ファイルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="2576b-114">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="2576b-115">また、次の構文を使用して、適切なクライアントフォルダーからスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="2576b-115">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="2576b-116">LyncPerfTool を直接実行するには、コマンドプロンプトを開き、コマンドラインで次のコマンドを入力します (この操作を初めて実行するときは、このトピックで後述する「メモ」に示すように、パフォーマンスカウンター regsvr32/i/n/s LyncPerfToolPerf を登録してください)。\<LyncPerfTool の設定: configxml\></span><span class="sxs-lookup"><span data-stu-id="2576b-116">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="2576b-117">構成ファイルの値をツールに表示するには、次のように、上記のコマンドに、次のようにして、/displayfile パラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="2576b-117">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="2576b-118">プロセスを終了するには、Ctrl + C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2576b-118">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2576b-119">LyncPerfTool を直接実行する前に、パフォーマンスカウンターを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2576b-119">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="2576b-120">次のコマンドを入力して、パフォーマンスカウンターを登録します。</span><span class="sxs-lookup"><span data-stu-id="2576b-120">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="2576b-121">開始する LyncPerfTool のすべてのインスタンスは、通常、1秒あたり1ユーザーの料金で、ユーザーのサインインを直ちに開始します。</span><span class="sxs-lookup"><span data-stu-id="2576b-121">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="2576b-122">プールのピークユーザーのサインイン率は約 12/秒です。</span><span class="sxs-lookup"><span data-stu-id="2576b-122">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="2576b-123">これは、ユーザーがまだサインインしている間、12個を超える LyncPerfTool インスタンスを同時に開始してはならないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2576b-123">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="2576b-124">1000ユーザーが完全にサインインするには、1秒あたり約20分かかります。</span><span class="sxs-lookup"><span data-stu-id="2576b-124">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2576b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2576b-125">See Also</span></span>


[<span data-ttu-id="2576b-126">ユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="2576b-126">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="2576b-127">ユーザープロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="2576b-127">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

