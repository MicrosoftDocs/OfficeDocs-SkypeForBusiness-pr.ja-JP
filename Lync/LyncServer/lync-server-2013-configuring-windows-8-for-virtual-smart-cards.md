---
title: 'Lync Server 2013: 仮想スマートカード用の Windows 8 の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177e5f9786b103c086630984be849c320801a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="d63e7-102">Lync Server 2013 で仮想スマートカードを使用するための Windows 8 の構成</span><span class="sxs-lookup"><span data-stu-id="d63e7-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d63e7-103">_**最終更新日:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="d63e7-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="d63e7-104">2 要素認証とスマート カード テクノロジを展開する場合に考慮する必要がある要素の 1 つは、実装コストです。</span><span class="sxs-lookup"><span data-stu-id="d63e7-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="d63e7-105">Windows 8 には新しいセキュリティ機能が数多く用意されています。また、最も重要な新機能の1つは仮想スマートカードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d63e7-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="d63e7-106">バージョン 1.2 仕様を満たす Trusted Platform Module (TPM) チップを搭載したコンピューターでは、ハードウェアの追加費用をかけずにスマート カード ログオンを活用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d63e7-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="d63e7-107">詳細については、「Windows 8 での仮想スマート[http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)カードの使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d63e7-107">For more information, see Using Virtual Smart Cards with Windows 8 at [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="d63e7-108">Windows 8 を仮想スマート カード用に構成するには</span><span class="sxs-lookup"><span data-stu-id="d63e7-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="d63e7-109">Lync 対応ユーザーの資格情報を使用して、Windows 8 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="d63e7-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="d63e7-110">Windows 8 のスタート画面で、画面の右下隅にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="d63e7-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="d63e7-111">[**検索**] オプションを選択し、「**Command Prompt**」を検索します。</span><span class="sxs-lookup"><span data-stu-id="d63e7-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="d63e7-112">[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d63e7-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="d63e7-113">次のコマンドを実行して、Trusted Platform Module (TPM) 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="d63e7-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="d63e7-114">TPM 管理コンソールで、TPM 仕様バージョンが 1.2 以上であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d63e7-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d63e7-115">相互運用性のある Trust Platform Module (TPM) が見つからないことを示すダイアログが表示された場合は、相互運用性のある TPM モジュールがコンピューターにインストールされていること、およびシステム BIOS で有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d63e7-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="d63e7-116">TPM 管理コンソールを閉じる</span><span class="sxs-lookup"><span data-stu-id="d63e7-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="d63e7-117">コマンド プロンプトで、次のコマンドを使用して新しい仮想スマート カードを作成します。</span><span class="sxs-lookup"><span data-stu-id="d63e7-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d63e7-118">仮想スマート カードを作成するときにカスタム PIN 値を指定するには、代わりに /pin プロンプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="d63e7-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="d63e7-119">コマンド プロンプトから、次のコマンドを実行してコンピューター管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="d63e7-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="d63e7-120">コンピューター管理コンソールで、[**デバイス管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d63e7-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="d63e7-121">[**スマート カード リーダー**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="d63e7-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="d63e7-122">新しい仮想スマート カード リーダーが正しく作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d63e7-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

