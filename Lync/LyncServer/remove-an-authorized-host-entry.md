---
title: 承認されたホストエントリを削除する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca9bc99382e904c398dbb7434b2ee6343ab661ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a><span data-ttu-id="76c59-102">承認されたホストエントリを削除する</span><span class="sxs-lookup"><span data-stu-id="76c59-102">Remove an authorized host entry</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76c59-103">_**最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="76c59-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="76c59-104">このトピックでは、従来の承認済みホストエントリ (Lync Server 2013 の*信頼済みアプリケーションエントリ*と呼ばれます) を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="76c59-104">This topic describes how to remove a legacy authorized host entry (known as a *trusted application entry* in Lync Server 2013).</span></span> <span data-ttu-id="76c59-105">リモート通話コントロールを Lync Server 2013 の展開に移行する場合、Office Communications Server 2007 R2 の展開で、すべての SIP/CSTA ゲートウェイの既存の承認済みホストエントリを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76c59-105">You must remove existing authorized host entries for any SIP/CSTA gateways in your Office Communications Server 2007 R2 deployment when you migrate remote call control to a Lync Server 2013 deployment.</span></span> <span data-ttu-id="76c59-106">既存の承認済みホストのエントリを削除するには、Office Communications Server 2007 R2 に含まれている管理ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76c59-106">You must use the administrative tools included with Office Communications Server 2007 R2 to remove the existing authorized host entries.</span></span>

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a><span data-ttu-id="76c59-107">Office Communications Server 2007 R2 の展開で承認されているホストエントリを削除するには</span><span class="sxs-lookup"><span data-stu-id="76c59-107">To remove an authorized host entry in an Office Communications Server 2007 R2 deployment</span></span>

1.  <span data-ttu-id="76c59-108">Office Communications Server 2007 R2 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="76c59-108">Open the Office Communications Server 2007 R2 administrative console.</span></span>

2.  <span data-ttu-id="76c59-109">ツリーを展開し、承認済みホストが作成されたプールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="76c59-109">Expand the tree and right-click the pool where the authorized host was created.</span></span>

3.  <span data-ttu-id="76c59-110">[**プロパティ**] をクリックし、[**フロントエンドプロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76c59-110">Click **Properties**, and then click **Front End Properties**.</span></span>

4.  <span data-ttu-id="76c59-111">[ **Host Authorization** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="76c59-111">Click the **Host Authorization** tab.</span></span>

5.  <span data-ttu-id="76c59-112">サーバーを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76c59-112">Select a server, and then click **Remove**.</span></span>

6.  <span data-ttu-id="76c59-113">[**プロパティ**] で [ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76c59-113">In **Properties**, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

