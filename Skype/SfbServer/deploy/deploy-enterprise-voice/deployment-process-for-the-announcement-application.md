---
title: ビジネス サーバーの Skype [お知らせ] アプリケーションの展開プロセス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 展開プロセスとビジネス サーバーのエンタープライズ VoIP は、Skype で知らせアプリケーションの手順を実行します。
ms.openlocfilehash: 96925df57a36373ee6f031b953f1933b3bac5681
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885600"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="a4acc-103">ビジネス サーバーの Skype [お知らせ] アプリケーションの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="a4acc-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="a4acc-104">展開プロセスとビジネス サーバーのエンタープライズ VoIP は、Skype で知らせアプリケーションの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a4acc-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="a4acc-105">アナウンス アプリケーションは、割り当てられていない拡張機能 (拡張機能、組織に有効ですが、ユーザーや電話に割り当てられていない) への呼び出しの動作を構成することを可能にするエンタープライズ VoIP 機能です。</span><span class="sxs-lookup"><span data-stu-id="a4acc-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="a4acc-106">たとえば、割り当てられていない番号に通話があった場合にメッセージを再生したり、別の通話先に転送したり、その両方を行ったりするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="a4acc-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="a4acc-107">エンタープライズ VoIP を展開する場合、フロント エンド サーバーまたは Standard Edition サーバー上の応答グループ アプリケーションの機能としてお知らせアプリケーションをインストールするとします。</span><span class="sxs-lookup"><span data-stu-id="a4acc-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a4acc-108">オーディオ ファイルをアップロードするか音声合成 (TTS) を構成して、割り当てられていない番号の表を構成し、アナウンスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4acc-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="a4acc-109">ここでは、アナウンス アプリケーションの展開に必要な手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a4acc-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="a4acc-110">アナウンスを構成する前に、エンタープライズ VoIP を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4acc-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="a4acc-111">アナウンス アプリケーションで必要なコンポーネントでは、インストールされ、エンタープライズ VoIP を展開するときに有効にすることがします。</span><span class="sxs-lookup"><span data-stu-id="a4acc-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="a4acc-112">**アナウンスの展開プロセス**</span><span class="sxs-lookup"><span data-stu-id="a4acc-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="a4acc-113">**段階**</span><span class="sxs-lookup"><span data-stu-id="a4acc-113">**Phase**</span></span>|<span data-ttu-id="a4acc-114">**手順**</span><span class="sxs-lookup"><span data-stu-id="a4acc-114">**Steps**</span></span>|<span data-ttu-id="a4acc-115">**Roles**</span><span class="sxs-lookup"><span data-stu-id="a4acc-115">**Roles**</span></span>|<span data-ttu-id="a4acc-116">**「展開」のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="a4acc-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a4acc-117">アナウンス設定の構成</span><span class="sxs-lookup"><span data-stu-id="a4acc-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="a4acc-118">オーディオ ファイルをレコーディングして読み込むか、音声合成 (TTS) を使用して、アナウンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a4acc-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="a4acc-119">割り当てられていない番号の表で、割り当てられていない番号の範囲を構成して、適切なアナウンスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a4acc-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="a4acc-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a4acc-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="a4acc-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a4acc-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="a4acc-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a4acc-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="a4acc-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a4acc-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="a4acc-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="a4acc-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="a4acc-125">作成またはビジネス サーバーの Skype でお知らせを削除します。</span><span class="sxs-lookup"><span data-stu-id="a4acc-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="a4acc-126">作成またはビジネス サーバーの Skype に割り当てられていない番号の範囲を変更します。</span><span class="sxs-lookup"><span data-stu-id="a4acc-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="a4acc-127">アナウンスの展開の確認</span><span class="sxs-lookup"><span data-stu-id="a4acc-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="a4acc-128">アナウンスを聞いてテストし、構成が予想どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4acc-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="a4acc-129">(省略可能)ビジネス用の Skype で知らせの展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="a4acc-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

