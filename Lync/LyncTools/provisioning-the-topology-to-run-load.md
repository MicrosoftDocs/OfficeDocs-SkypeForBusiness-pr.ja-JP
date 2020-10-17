---
title: 負荷を実行するためのトポロジのプロビジョニング
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45b1c9d320ef35555e83bbd8851d77e00a452631
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509110"
---
# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="d4765-102">負荷を実行するためのトポロジのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="d4765-102">Provisioning the Topology to Run Load</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4765-103">_**トピックの最終更新日:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="d4765-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

<span data-ttu-id="d4765-104">既存の設定と Lync Server 2013 の構成によっては、環境を次のように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4765-104">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="d4765-105">Windows PowerShell 実行ポリシーを無制限に設定します。</span><span class="sxs-lookup"><span data-stu-id="d4765-105">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="d4765-106">実行ポリシーの設定を確認するには、Lync Server 管理シェルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4765-106">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="d4765-107">このコマンドで無制限の値が返されない場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4765-107">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="d4765-108">Lync Server 2013 を効果的に構成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4765-108">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="d4765-109">Lync Server 2013 トポロジ (コンピューター名、サービスインスタンス、サイト名、ポリシーなど) について理解していること。</span><span class="sxs-lookup"><span data-stu-id="d4765-109">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="d4765-110">応答グループのハントグループ (たとえば、SIP Uri) など、グループに作成された一部のユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d4765-110">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="d4765-111">コマンドラインからスクリプトを実行するには、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="d4765-111">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="d4765-112">通常、このパッケージのスクリプトのいずれかが実行されると、スクリプトから得られたトレースは、スクリプトが呼び出されたパス内のファイルに格納され、 \<scriptname\> $h $ m $s.txt という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="d4765-112">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="d4765-113">たとえば、ArchivingPolicy.ps1 を午後12:15 時に実行します。</span><span class="sxs-lookup"><span data-stu-id="d4765-113">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="d4765-114">は、ArchivingPolicy121500.txt などのログファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="d4765-114">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="d4765-115">最後に、サーバーを構成するための例を提供していますが、負荷の実行が終了したら、構成を変更または削除する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d4765-115">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

