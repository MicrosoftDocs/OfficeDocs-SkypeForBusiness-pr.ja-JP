---
title: Skype for Business でのお知らせアプリケーションの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Skype for Business Server エンタープライズ Voip のお知らせアプリケーションの計画。組織内の未割り当ての電話番号への通話で何を行うのかを設定します。 また、オーディオ ファイルの要件についても説明します。
ms.openlocfilehash: d160878030fad30dd3e91b78f54ffcdab722299f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803267"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a><span data-ttu-id="0cfec-104">Skype for Business でのお知らせアプリケーションの計画</span><span class="sxs-lookup"><span data-stu-id="0cfec-104">Plan for the Announcement application in Skype for Business</span></span>

<span data-ttu-id="0cfec-105">Skype for Business Server エンタープライズ Voip のお知らせアプリケーションの計画。組織内の未割り当ての電話番号への通話で何を行うのかを設定します。</span><span class="sxs-lookup"><span data-stu-id="0cfec-105">Planning for the announcement application in Skype for Business Server Enterprise Voice, which configures what to do with phone calls to unassigned phone numbers in your organizations.</span></span> <span data-ttu-id="0cfec-106">また、オーディオ ファイルの要件についても説明します。</span><span class="sxs-lookup"><span data-stu-id="0cfec-106">Includes audio file requirements.</span></span>

<span data-ttu-id="0cfec-107">Skype for Business Server アナウンスメントアプリケーションを使用すると、ダイヤルされた番号が組織で有効であるが、ユーザーまたは電話に割り当てられていない場合に、着信通話の処理を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="0cfec-107">The Skype for Business Server Announcement application enables you to configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or a phone.</span></span> <span data-ttu-id="0cfec-108">これらの通話を事前に設定しておいた転送先 (電話番号、SIP URI、またはボイス メール) に転送するか、音声アナウンスを再生するか、またはその両方を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0cfec-108">You can transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="0cfec-109">アナウンス アプリケーションを使用することで、発信者が誤ってダイヤルしたり、話し中の音が流されたり、または SIP クライアントがエラー メッセージを受け取ったりするような状況を避けることができます。</span><span class="sxs-lookup"><span data-stu-id="0cfec-109">The Announcement application helps you avoid the situations in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="0cfec-110">このセクションには、アナウンスメントアプリケーションに固有の計画情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="0cfec-110">This section includes planning information that is specific to the Announcement application</span></span>

<span data-ttu-id="0cfec-111">アナウンスメントアプリケーションを展開するときに、割り当てられていない番号をダイヤルしたときに実行されるアクションを決定する、割り当てられていない番号テーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cfec-111">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="0cfec-112">割り当てられていない番号テーブルには、組織で有効な電話番号の範囲が含まれており、各範囲を処理するアナウンスメントアプリケーションが指定されています。</span><span class="sxs-lookup"><span data-stu-id="0cfec-112">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="0cfec-113">発信者が組織で有効な電話番号をダイヤルしたが、すべてのユーザーに割り当てられていない場合、Skype for Business Server は、割り当てられていない番号ルーティングテーブルの番号を検索し、その番号がどの範囲にあるかを特定して、通話をその範囲に対して指定されたアナウンスメントアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="0cfec-113">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Skype for Business Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="0cfec-114">アナウンスメントアプリケーションは、通話に応答し、音声メッセージを再生し (設定している場合)、電話を切断するか、オペレーターなどの事前に定義された宛先に転送します。</span><span class="sxs-lookup"><span data-stu-id="0cfec-114">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="0cfec-115">Skype for Business Server Management Shell コマンドレットを使用して、複数の音声メッセージを構成したり、送信先を転送したりできます。</span><span class="sxs-lookup"><span data-stu-id="0cfec-115">You can use Skype for Business Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="0cfec-p105">割り当てられていない番号の表の構成方法はその使用方法によって異なります。現在使用されていない特定の番号があり、各番号用に作成したメッセージを再生する必要がある場合、これらの特定の番号を割り当てられていない番号の表に入力できます。たとえば、顧客サービス デスクの番号を変更した場合、古い顧客サービス番号を入力して、新しい番号を知らせるアナウンスをその番号に関連付けることができます。組織から離れた従業員の番号など、割り当てられていない番号を呼び出す発信者に対して一般的なメッセージを再生する必要がある場合、組織内のすべての有効な内線番号の範囲を入力できます。割り当てられていない番号の表は、発信者が現在割り当てられていない番号をダイヤルすると常に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0cfec-p105">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

## <a name="deployment-and-requirements"></a><span data-ttu-id="0cfec-121">展開と要件</span><span class="sxs-lookup"><span data-stu-id="0cfec-121">Deployment and requirements</span></span>

<span data-ttu-id="0cfec-122">このアナウンスメントアプリケーションは、応答グループアプリケーションと共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0cfec-122">Tthe Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="0cfec-123">お知らせと応答グループのアプリケーションは、エンタープライズ Voip 展開の標準的なコンポーネントです。エンタープライズボイスを展開すると、これらの両方のアプリケーションが自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="0cfec-123">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="0cfec-124">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="0cfec-124">Software requirements</span></span>

<span data-ttu-id="0cfec-125">アナウンスメントアプリケーションを実行するすべてのフロントエンドサーバーまたは標準エディションのサーバーは、windows server 2008 R2 を実行しているサーバー、または Windows Server 2012 を実行しているサーバーの Microsoft メディアファンデーションに Windows Media Format ランタイムをインストールする必要があります。Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="0cfec-125">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="0cfec-126">Windows Server 2008 R2 の場合、windows Media 形式ランタイムは Windows デスクトップエクスペリエンスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0cfec-126">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="0cfec-127">Windows media Format Runtime または Microsoft メディアファンデーションは、アナウンスメントアプリケーションがお知らせや音楽を再生するために Windows Media オーディオ (.wma) ファイルを使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="0cfec-127">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

### <a name="port-requirements"></a><span data-ttu-id="0cfec-128">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="0cfec-128">Port Requirements</span></span>

<span data-ttu-id="0cfec-129">アナウンスメントアプリケーションは、SIP リスニング要求に**ポート 5071**を使用します。</span><span class="sxs-lookup"><span data-stu-id="0cfec-129">The Announcement application uses **Port 5071** for SIP listening requests.</span></span>

> [!NOTE]
> <span data-ttu-id="0cfec-130">このポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="0cfec-130">This port is the default setting, which you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="0cfec-131">このコマンドレットの詳細については、「Skype for Business Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cfec-131">For details about this cmdlet, see the Skype for Business Server Management Shell documentation.</span></span>

### <a name="audio-file-requirements"></a><span data-ttu-id="0cfec-132">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="0cfec-132">Audio File Requirements</span></span>

<span data-ttu-id="0cfec-133">アナウンスメントアプリケーションは、音楽とお知らせのウェーブ (.wav) ファイル形式と Windows Media オーディオ (.wma) ファイル形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0cfec-133">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="0cfec-134">アナウンスメントアプリケーションのオーディオファイルの要件は、応答グループアプリケーションの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="0cfec-134">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="0cfec-135">詳細は、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cfec-135">For details, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>


