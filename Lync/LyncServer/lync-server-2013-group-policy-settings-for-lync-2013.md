---
title: 'Lync Server 2013: Lync 2013 のグループポリシー設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937869dffc3dfecc994f3c9ce819e1a644c88abe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="97249-102">Lync 2013 のグループポリシー設定</span><span class="sxs-lookup"><span data-stu-id="97249-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97249-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="97249-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="97249-104">以前のバージョンの Lync および Office Communicator では、スタンドアロンの Communicator 管理用テンプレートを使用してクライアントグループポリシー設定を構成できました。</span><span class="sxs-lookup"><span data-stu-id="97249-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="97249-105">Lync 2013 では、新しい管理用テンプレートファイル (admx および adml ファイル) が Office グループポリシー管理用テンプレートと共に含まれています。</span><span class="sxs-lookup"><span data-stu-id="97249-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="97249-106">Lync 2013 ファイルと adml ファイルを使用すると、テンプレートをダウンロードして、すべての Office プログラムおよび言語パックのグループポリシー設定を一元管理できます。</span><span class="sxs-lookup"><span data-stu-id="97249-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="97249-107">詳細については、Office 2013 のドキュメントの「Office 2013 管理用テンプレートファイル (ADMX, ADML <https://go.microsoft.com/fwlink/p/?linkid=267516>)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97249-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="97249-108">クライアント ブートストラップ ポリシー</span><span class="sxs-lookup"><span data-stu-id="97249-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="97249-109">ユーザーが初めてサーバーにサインインする前に、幾つかのクライアント ブートストラップ ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97249-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="97249-110">これらのポリシーは、クライアントがサインインする前に有効になり、サーバーからインバンド プロビジョニング設定を受け取るようになるため、グループ ポリシーを使って構成できます。</span><span class="sxs-lookup"><span data-stu-id="97249-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="97249-111">詳細については、「展開」のドキュメントの「 [Lync Server 2013 でのクライアントブートストラップポリシーの構成](lync-server-2013-configuring-client-bootstrapping-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97249-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

