---
title: 'Lync Server 2013: 音声ポリシーと PSTN 使用法レコードを構成して、通話機能と特権を承認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies and PSTN usage records to authorize calling features and privileges
ms:assetid: 63f22010-a3d7-4cbd-86e8-6fc0e13c2b84
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398450(v=OCS.15)
ms:contentKeyID: 48184307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 339eba57121b475732794b15c2c5d16dced303ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges-in-lync-server-2013"></a><span data-ttu-id="b37d4-102">Lync Server 2013 での通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="b37d4-102">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b37d4-103">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="b37d4-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="b37d4-104">音声ポリシー\*\* は、一連の通話機能を有効にし、1 つまたは複数の PSTN 使用法レコードを関連付けして、そのポリシーを割り当てられているユーザーの通話機能とアクセス許可を定義します。</span><span class="sxs-lookup"><span data-stu-id="b37d4-104">A *voice policy* enables a set of calling features and associates one or more PSTN usage records to define the calling features and permissions of users who are assigned the policy.</span></span>

<span data-ttu-id="b37d4-p101">音声ポリシーのスコープは、サイト\*\* またはユーザー\*\* のどちらかになります。サイト スコープはネットワーク サイトの既定の機能とアクセス許可を定義し、ユーザー スコープはユーザー単位またはグループ単位で割り当てられる機能とアクセス許可を定義します。音声ポリシーが割り当てられていないユーザーは、自動的にグローバル ポリシーが割り当てられます。グローバル ポリシーは製品と共にインストールされる既定の音声ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b37d4-p101">Voice policy scope can be either *Site* (which defines the default features and permissions for a network site) or *User* (which defines the features and permissions to be assigned on a per-user or group basis). Users not assigned to a voice policy will automatically be assigned to the global policy, which is the default voice policy that is installed with the product.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b37d4-107">詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-voice-policies.md">Voice policies In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b37d4-107">For details, see <A href="lync-server-2013-voice-policies.md">Voice policies in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b37d4-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b37d4-108">In This Section</span></span>

  - [<span data-ttu-id="b37d4-109">Lync Server 2013 で音声ポリシーを作成し、PSTN 使用法レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="b37d4-109">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="b37d4-110">Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="b37d4-110">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="b37d4-111">Lync Server 2013 でのボイスメールエスケープの構成</span><span class="sxs-lookup"><span data-stu-id="b37d4-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

