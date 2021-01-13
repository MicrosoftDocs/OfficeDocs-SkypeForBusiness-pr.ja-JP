---
title: Skype for Business Server でのアナウンス アプリケーションの展開プロセス
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Skype for Business Server エンタープライズ VoIP でのアナウンス アプリケーションの展開プロセスとエンタープライズ VoIP。
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812307"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="f4c0a-103">Skype for Business Server でのアナウンス アプリケーションの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="f4c0a-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="f4c0a-104">Skype for Business Server エンタープライズ VoIP でのアナウンス アプリケーションの展開プロセスとエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="f4c0a-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="f4c0a-105">アナウンス アプリケーションは エンタープライズ VoIP 機能で、割り当てられていない内線番号への呼び出しに対する処理を構成できます (組織で有効で、ユーザーや電話には割り当てられていない内線番号)。</span><span class="sxs-lookup"><span data-stu-id="f4c0a-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="f4c0a-106">たとえば、割り当てられていない番号に通話があった場合にメッセージを再生したり、別の通話先に転送したり、その両方を行ったりするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="f4c0a-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="f4c0a-107">アナウンス アプリケーションは、展開時にフロント エンド サーバーまたは Standard Edition サーバーに応答グループ アプリケーションの機能としてエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="f4c0a-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f4c0a-108">オーディオ ファイルをアップロードするか音声合成 (TTS) を構成して、割り当てられていない番号の表を構成し、アナウンスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c0a-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="f4c0a-109">このセクションでは、アナウンス アプリケーションの展開に関連する手順の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4c0a-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="f4c0a-110">アナウンスを構成する前エンタープライズ VoIPを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c0a-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="f4c0a-111">アナウンス アプリケーションで必要なコンポーネントは、展開時にインストールされエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="f4c0a-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="f4c0a-112">**アナウンス展開プロセス**</span><span class="sxs-lookup"><span data-stu-id="f4c0a-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="f4c0a-113">**フェーズ**</span><span class="sxs-lookup"><span data-stu-id="f4c0a-113">**Phase**</span></span>|<span data-ttu-id="f4c0a-114">**手順**</span><span class="sxs-lookup"><span data-stu-id="f4c0a-114">**Steps**</span></span>|<span data-ttu-id="f4c0a-115">**Roles**</span><span class="sxs-lookup"><span data-stu-id="f4c0a-115">**Roles**</span></span>|<span data-ttu-id="f4c0a-116">**展開のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="f4c0a-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f4c0a-117">アナウンス設定を構成する</span><span class="sxs-lookup"><span data-stu-id="f4c0a-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="f4c0a-118">オーディオ ファイルを録音してアップロードするか、音声合成 (TTS) を使用してアナウンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f4c0a-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="f4c0a-119">割り当てられていない番号の表の割り当てられていない番号の範囲を構成し、それらを適切なアナウンスに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="f4c0a-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="f4c0a-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f4c0a-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="f4c0a-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f4c0a-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="f4c0a-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f4c0a-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="f4c0a-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f4c0a-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="f4c0a-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="f4c0a-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="f4c0a-125">Skype for Business Server でアナウンスを作成または削除する</span><span class="sxs-lookup"><span data-stu-id="f4c0a-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="f4c0a-126">Skype for Business Server で割り当てられていない番号範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="f4c0a-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="f4c0a-127">アナウンスの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="f4c0a-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="f4c0a-128">アナウンスを聞いてテストし、構成が期待通り動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="f4c0a-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="f4c0a-129">(省略可能)Skype for Business でのアナウンスの展開の確認</span><span class="sxs-lookup"><span data-stu-id="f4c0a-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

