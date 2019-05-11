---
title: ビジネス用の Skype で知らせアプリケーションの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: ビジネス サーバーのエンタープライズ VoIP の Skype [お知らせ] アプリケーションの計画を構成、組織に割り当てられていない電話番号への電話の処理をします。 また、オーディオ ファイルの要件についても説明します。
ms.openlocfilehash: 0e0a020a1301e8b8369ffdecc2e9e67d74b5e7b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33909359"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a><span data-ttu-id="05a22-104">ビジネス用の Skype で知らせアプリケーションの計画</span><span class="sxs-lookup"><span data-stu-id="05a22-104">Plan for the Announcement application in Skype for Business</span></span>

<span data-ttu-id="05a22-105">ビジネス サーバーのエンタープライズ VoIP の Skype [お知らせ] アプリケーションの計画を構成、組織に割り当てられていない電話番号への電話の処理をします。</span><span class="sxs-lookup"><span data-stu-id="05a22-105">Planning for the announcement application in Skype for Business Server Enterprise Voice, which configures what to do with phone calls to unassigned phone numbers in your organizations.</span></span> <span data-ttu-id="05a22-106">また、オーディオ ファイルの要件についても説明します。</span><span class="sxs-lookup"><span data-stu-id="05a22-106">Includes audio file requirements.</span></span>

<span data-ttu-id="05a22-107">サーバー アナウンスをビジネス アプリケーションの Skype を使用すると、ダイヤルの番号は、組織に有効ですが、ユーザーや電話に割り当てられていない場合は、電話の着信呼び出しの処理を構成できます。</span><span class="sxs-lookup"><span data-stu-id="05a22-107">The Skype for Business Server Announcement application enables you to configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or a phone.</span></span> <span data-ttu-id="05a22-108">これらの通話を事前に設定しておいた転送先 (電話番号、SIP URI、またはボイス メール) に転送するか、音声アナウンスを再生するか、またはその両方を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="05a22-108">You can transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="05a22-109">アナウンス アプリケーションを使用することで、発信者が誤ってダイヤルしたり、話し中の音が流されたり、または SIP クライアントがエラー メッセージを受け取ったりするような状況を避けることができます。</span><span class="sxs-lookup"><span data-stu-id="05a22-109">The Announcement application helps you avoid the situations in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="05a22-110">ここでは、アナウンス アプリケーション固有の情報を計画</span><span class="sxs-lookup"><span data-stu-id="05a22-110">This section includes planning information that is specific to the Announcement application</span></span>

<span data-ttu-id="05a22-111">アナウンス アプリケーションを展開するときは、他のユーザーに割り当てられていない番号をダイヤルするときに実行されるアクションを決定する、割り当てられていない番号テーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05a22-111">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="05a22-112">表には、未使用の番号では、組織に対して有効な電話番号の範囲が含まれていて、アナウンス アプリケーションはそれぞれの範囲を処理を指定します。</span><span class="sxs-lookup"><span data-stu-id="05a22-112">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="05a22-113">呼び出し元は、組織にとって有効ですが、すべてのユーザーに割り当てられていない電話番号をダイヤルするとき Skype ビジネス サーバーが割り当てられていない番号のルーティング テーブル内の数値を検索の範囲を識別する数の内、およびへの呼び出しをルーティングしますお知らせアプリケーションがその範囲に指定されています。</span><span class="sxs-lookup"><span data-stu-id="05a22-113">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Skype for Business Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="05a22-114">アナウンス アプリケーション呼び出しに応答し (するには、構成されている) 場合は、オーディオ メッセージを再生し通話を切断するか、転送先が事前に定義された場合など、オペレーターに。</span><span class="sxs-lookup"><span data-stu-id="05a22-114">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="05a22-115">複数のオーディオ メッセージを構成する、または送信先に転送する Skype ビジネス サーバー管理シェル コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="05a22-115">You can use Skype for Business Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="05a22-p105">割り当てられていない番号の表の構成方法はその使用方法によって異なります。現在使用されていない特定の番号があり、各番号用に作成したメッセージを再生する必要がある場合、これらの特定の番号を割り当てられていない番号の表に入力できます。たとえば、顧客サービス デスクの番号を変更した場合、古い顧客サービス番号を入力して、新しい番号を知らせるアナウンスをその番号に関連付けることができます。組織から離れた従業員の番号など、割り当てられていない番号を呼び出す発信者に対して一般的なメッセージを再生する必要がある場合、組織内のすべての有効な内線番号の範囲を入力できます。割り当てられていない番号の表は、発信者が現在割り当てられていない番号をダイヤルすると常に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="05a22-p105">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

## <a name="deployment-and-requirements"></a><span data-ttu-id="05a22-121">展開と要件</span><span class="sxs-lookup"><span data-stu-id="05a22-121">Deployment and requirements</span></span>

<span data-ttu-id="05a22-122">単位のお知らせのアプリケーションは、応答グループ アプリケーションと共に自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="05a22-122">Tthe Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="05a22-123">アナウンスおよび応答グループ アプリケーションは、エンタープライズ VoIP の展開の標準的なコンポーネント: とエンタープライズ VoIP を展開すると、両方のこれらのアプリケーションは自動的に配置します。</span><span class="sxs-lookup"><span data-stu-id="05a22-123">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="05a22-124">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="05a22-124">Software requirements</span></span>

<span data-ttu-id="05a22-125">アナウンス アプリケーションを実行しているすべてのフロント エンド サーバーまたは Standard Edition サーバーに Windows Server 2012 を実行しているサーバーの Windows Server 2008 R2、または Microsoft メディア ファンデーションを実行しているサーバーがインストールされている Windows Media フォーマット ランタイムが必要かWindows Server 2012 R2 です。</span><span class="sxs-lookup"><span data-stu-id="05a22-125">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="05a22-126">Windows Server 2008 R2、Windows デスクトップのエクスペリエンスの一部として、Windows Media フォーマット ランタイムがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="05a22-126">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="05a22-127">Windows Media フォーマット ランタイムや Microsoft メディア ファンデーションは、お知らせや音楽の発表のアプリケーションを再生する Windows Media オーディオ (.wma) ファイルに必要です。</span><span class="sxs-lookup"><span data-stu-id="05a22-127">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

### <a name="port-requirements"></a><span data-ttu-id="05a22-128">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="05a22-128">Port Requirements</span></span>

<span data-ttu-id="05a22-129">アナウンス アプリケーションでは、SIP リッスン要求に**ポート 5071**を使用します。</span><span class="sxs-lookup"><span data-stu-id="05a22-129">The Announcement application uses **Port 5071** for SIP listening requests.</span></span>

> [!NOTE]
> <span data-ttu-id="05a22-130">このポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="05a22-130">This port is the default setting, which you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="05a22-131">詳細については、このコマンドレットは、サーバー管理シェルのビジネス ドキュメントの Skype を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05a22-131">For details about this cmdlet, see the Skype for Business Server Management Shell documentation.</span></span>

### <a name="audio-file-requirements"></a><span data-ttu-id="05a22-132">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="05a22-132">Audio File Requirements</span></span>

<span data-ttu-id="05a22-133">アナウンス アプリケーションは、Wave (.wav) ファイル形式および Windows Media オーディオ (.wma) をサポートしている音楽やお知らせのファイル形式です。</span><span class="sxs-lookup"><span data-stu-id="05a22-133">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="05a22-134">アナウンス アプリケーションのオーディオ ファイルの要件は、応答グループ アプリケーションの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="05a22-134">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="05a22-135">詳細は、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05a22-135">For details, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>


