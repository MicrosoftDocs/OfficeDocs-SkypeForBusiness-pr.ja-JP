---
title: ロードを実行するトポロジのプロビジョニング
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026915b4a08073e96d29b32278adc4e260eaaea4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="4d6e8-102">ロードを実行するトポロジのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="4d6e8-102">Provisioning the Topology to Run Load</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d6e8-103">_**最終更新日:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="4d6e8-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

## <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="4d6e8-104">ロードを実行するトポロジのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="4d6e8-104">Provisioning the Topology to Run Load</span></span>

<span data-ttu-id="4d6e8-105">Lync Server 2013 の既存の設定と構成によっては、お使いの環境で次の変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="4d6e8-106">Windows PowerShell の実行ポリシーを無制限に設定します。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="4d6e8-107">実行ポリシーの設定を確認するには、Lync Server 管理シェルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="4d6e8-108">このコマンドを実行しても無制限の値が返されない場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="4d6e8-109">Lync Server 2013 を効果的に構成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="4d6e8-110">Lync Server 2013 トポロジ (コンピューター名、サービスインスタンス、サイト名、ポリシーなど) について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="4d6e8-111">応答グループのハントグループ (SIP Uri など) など、グループに作成されたユーザーの一部を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="4d6e8-112">コマンドラインからスクリプトを実行するには、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="4d6e8-113">通常、このパッケージのいずれかのスクリプトが実行されると、スクリプトからの結果のトレースは、scriptname \<\>$h $ m $ s .txt という名前のスクリプトが呼び出された同じパスのファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="4d6e8-114">たとえば、ArchivingPolicy を午後12:15 時に実行します。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="4d6e8-115">ArchivingPolicy121500 などのログファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="4d6e8-116">最後に、サーバーを構成するための例を用意しましたが、ロードの実行が完了した後で構成を変更または削除する責任があります。</span><span class="sxs-lookup"><span data-stu-id="4d6e8-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

