---
title: 'Lync Server 2013: 通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成'
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
ms.openlocfilehash: 7b9f7da3f8560ae0a897211405d686d9ed35101e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges-in-lync-server-2013"></a><span data-ttu-id="a1a0b-102">Lync Server 2013 での通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="a1a0b-102">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1a0b-103">_**最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="a1a0b-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="a1a0b-104">*音声ポリシー*は、通話機能のセットを有効にし、1つ以上の PSTN 利用状況レコードを関連付けて、ポリシーを割り当てられたユーザーの呼び出し機能と権限を定義します。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-104">A *voice policy* enables a set of calling features and associates one or more PSTN usage records to define the calling features and permissions of users who are assigned the policy.</span></span>

<span data-ttu-id="a1a0b-105">ボイスポリシーのスコープは、(ネットワークサイトの既定の機能と権限を定義する) いずれかの*サイト*または*ユーザー* (ユーザーごとまたはグループごとに割り当てる機能と権限を定義する) のいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-105">Voice policy scope can be either *Site* (which defines the default features and permissions for a network site) or *User* (which defines the features and permissions to be assigned on a per-user or group basis).</span></span> <span data-ttu-id="a1a0b-106">ボイスポリシーに割り当てられていないユーザーは、グローバルポリシー (製品と共にインストールされる既定の音声ポリシー) に自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-106">Users not assigned to a voice policy will automatically be assigned to the global policy, which is the default voice policy that is installed with the product.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a1a0b-107">詳細については、計画ドキュメントの「 <A href="lync-server-2013-voice-policies.md">Lync Server 2013 のボイスポリシー</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-107">For details, see <A href="lync-server-2013-voice-policies.md">Voice policies in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a1a0b-108">このセクション中</span><span class="sxs-lookup"><span data-stu-id="a1a0b-108">In This Section</span></span>

  - [<span data-ttu-id="a1a0b-109">Lync Server 2013 で音声ポリシーを作成し、PSTN 使用状況レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="a1a0b-109">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="a1a0b-110">Lync Server 2013 で音声ポリシーを変更し、PSTN 使用状況レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="a1a0b-110">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="a1a0b-111">Lync Server 2013 でボイスメールのエスケープを構成する</span><span class="sxs-lookup"><span data-stu-id="a1a0b-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

