---
title: 負荷を実行するためのトポロジのプロビジョニング
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9b81708cbd518b43247c4324ecc651a4089c3ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="12cd3-102">負荷を実行するためのトポロジのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="12cd3-102">Provisioning the Topology to Run Load</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12cd3-103">_**トピックの最終更新日:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="12cd3-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

## <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="12cd3-104">負荷を実行するためのトポロジのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="12cd3-104">Provisioning the Topology to Run Load</span></span>

<span data-ttu-id="12cd3-105">既存の設定と Lync Server 2013 の構成によっては、環境を次のように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12cd3-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="12cd3-106">Windows PowerShell 実行ポリシーを無制限に設定します。</span><span class="sxs-lookup"><span data-stu-id="12cd3-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="12cd3-107">実行ポリシーの設定を確認するには、Lync Server 管理シェルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="12cd3-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="12cd3-108">このコマンドで無制限の値が返されない場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="12cd3-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="12cd3-109">Lync Server 2013 を効果的に構成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="12cd3-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="12cd3-110">Lync Server 2013 トポロジ (コンピューター名、サービスインスタンス、サイト名、ポリシーなど) について理解していること。</span><span class="sxs-lookup"><span data-stu-id="12cd3-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="12cd3-111">応答グループのハントグループ (たとえば、SIP Uri) など、グループに作成された一部のユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="12cd3-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="12cd3-112">コマンドラインからスクリプトを実行するには、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="12cd3-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="12cd3-113">通常、このパッケージのいずれかのスクリプトを実行した後、スクリプトから得られたトレースは、スクリプトが呼び出されたパス内のファイルに格納さ\<れ\>ます。これは、scriptname $h $ m $ s .txt という名前です。</span><span class="sxs-lookup"><span data-stu-id="12cd3-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="12cd3-114">たとえば、ArchivingPolicy を午後12:15 時に実行したとします。</span><span class="sxs-lookup"><span data-stu-id="12cd3-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="12cd3-115">は、ArchivingPolicy121500 などのログファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="12cd3-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="12cd3-116">最後に、サーバーを構成するための例を提供していますが、負荷の実行が終了したら、構成を変更または削除する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="12cd3-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

