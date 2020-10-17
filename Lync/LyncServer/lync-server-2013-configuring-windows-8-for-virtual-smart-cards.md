---
title: 'Lync Server 2013: 仮想スマートカード用の Windows 8 の構成'
description: 'Lync Server 2013: 仮想スマートカード用の Windows 8 の構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112047f91a20dd552c628fb33eba7bb9ad3d0f01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542163"
---
# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="7fa71-103">Lync Server 2013 で仮想スマートカードを使用するための Windows 8 の構成</span><span class="sxs-lookup"><span data-stu-id="7fa71-103">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fa71-104">_**トピックの最終更新日:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="7fa71-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="7fa71-105">2要素認証とスマートカードテクノロジを展開する際に考慮する要因の1つは、実装コストです。</span><span class="sxs-lookup"><span data-stu-id="7fa71-105">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="7fa71-106">Windows 8 には新しいセキュリティ機能がいくつか用意されており、最も興味深い新機能の1つは仮想スマートカードのサポートです。</span><span class="sxs-lookup"><span data-stu-id="7fa71-106">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="7fa71-107">仕様バージョン1.2 を満たすトラステッドプラットフォームモジュール (TPM) チップを備えたコンピューターの場合、組織は、ハードウェアに追加の投資を行わずにスマートカードログオンの利点を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="7fa71-107">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="7fa71-108">詳細については、「Windows 8 での仮想スマートカードの使用」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365) 。</span><span class="sxs-lookup"><span data-stu-id="7fa71-108">For more information, see Using Virtual Smart Cards with Windows 8 at [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="7fa71-109">仮想スマートカード用に Windows 8 を構成するには</span><span class="sxs-lookup"><span data-stu-id="7fa71-109">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="7fa71-110">Lync が有効なユーザーの資格情報を使用して、Windows 8 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="7fa71-110">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="7fa71-111">Windows 8 のスタート画面で、カーソルを画面の右下隅に移動します。</span><span class="sxs-lookup"><span data-stu-id="7fa71-111">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="7fa71-112">**検索**オプションを選択し、**コマンドプロンプト**を検索します。</span><span class="sxs-lookup"><span data-stu-id="7fa71-112">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="7fa71-113">[ **コマンドプロンプト**] を右クリックし、[ **管理者として実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fa71-113">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="7fa71-114">次のコマンドを実行して、トラステッドプラットフォームモジュール (TPM) 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="7fa71-114">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="7fa71-115">TPM 管理コンソールから、TPM 仕様バージョンが少なくとも1.2 であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fa71-115">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7fa71-116">互換性のある信頼できるプラットフォームモジュール (TPM) が見つからないことを示すダイアログボックスが表示された場合は、コンピューターに互換性のある TPM モジュールがあり、システム BIOS で有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7fa71-116">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="7fa71-117">TPM 管理コンソールを閉じる</span><span class="sxs-lookup"><span data-stu-id="7fa71-117">Close the TPM management console</span></span>

8.  <span data-ttu-id="7fa71-118">コマンドプロンプトで、次のコマンドを使用して、新しい仮想スマートカードを作成します。</span><span class="sxs-lookup"><span data-stu-id="7fa71-118">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7fa71-119">仮想スマートカードを作成するときにカスタムの PIN 値を指定するには、代わりに [/pin プロンプト] を使用します。</span><span class="sxs-lookup"><span data-stu-id="7fa71-119">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="7fa71-120">コマンドプロンプトで、次のコマンドを実行して、コンピューターの管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="7fa71-120">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="7fa71-121">[コンピューターの管理] コンソールで、[ **デバイス管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fa71-121">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="7fa71-122">[ **スマートカード読み取り装置**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="7fa71-122">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="7fa71-123">新しい仮想スマートカードリーダーが正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fa71-123">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

