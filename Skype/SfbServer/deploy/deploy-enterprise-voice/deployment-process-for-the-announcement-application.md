---
title: Skype for Business Server のアナウンスメントアプリケーションの展開プロセス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Skype for Business Server Enterprise Voice の展開プロセスとお知らせアプリケーションの手順。
ms.openlocfilehash: 77d15c4ce749a97ec11ed5d5e083ccf6fa2aecfa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275609"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="b998b-103">Skype for Business Server のアナウンスメントアプリケーションの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="b998b-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="b998b-104">Skype for Business Server Enterprise Voice の展開プロセスとお知らせアプリケーションの手順。</span><span class="sxs-lookup"><span data-stu-id="b998b-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b998b-105">アナウンスメントアプリケーションは、割り当てられていない拡張子 (組織に対して有効であり、ユーザーまたは電話に割り当てられていない拡張機能) への呼び出しを構成できるエンタープライズ Voip 機能です。</span><span class="sxs-lookup"><span data-stu-id="b998b-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="b998b-106">たとえば、割り当てられていない番号に通話があった場合にメッセージを再生したり、別の通話先に転送したり、その両方を行ったりするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="b998b-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="b998b-107">お知らせアプリケーションは、エンタープライズボイスの展開時に、フロントエンドサーバーまたは Standard Edition サーバー上の応答グループアプリケーションの機能としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b998b-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b998b-108">オーディオ ファイルをアップロードするか音声合成 (TTS) を構成して、割り当てられていない番号の表を構成し、アナウンスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b998b-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="b998b-109">このセクションでは、アナウンスメントアプリケーションの展開に関連する手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="b998b-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="b998b-110">お知らせを構成する前に、エンタープライズボイスを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b998b-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="b998b-111">[エンタープライズ Voip] を展開すると、アナウンスメントアプリケーションで必要なコンポーネントがインストールされて有効になります。</span><span class="sxs-lookup"><span data-stu-id="b998b-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="b998b-112">**アナウンスの展開プロセス**</span><span class="sxs-lookup"><span data-stu-id="b998b-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="b998b-113">**段階**</span><span class="sxs-lookup"><span data-stu-id="b998b-113">**Phase**</span></span>|<span data-ttu-id="b998b-114">**手順**</span><span class="sxs-lookup"><span data-stu-id="b998b-114">**Steps**</span></span>|<span data-ttu-id="b998b-115">**Roles**</span><span class="sxs-lookup"><span data-stu-id="b998b-115">**Roles**</span></span>|<span data-ttu-id="b998b-116">**「展開」のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="b998b-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b998b-117">アナウンス設定の構成</span><span class="sxs-lookup"><span data-stu-id="b998b-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="b998b-118">オーディオ ファイルをレコーディングして読み込むか、音声合成 (TTS) を使用して、アナウンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b998b-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="b998b-119">割り当てられていない番号の表で、割り当てられていない番号の範囲を構成して、適切なアナウンスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="b998b-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="b998b-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b998b-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="b998b-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b998b-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="b998b-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b998b-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="b998b-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b998b-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="b998b-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="b998b-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="b998b-125">Skype for Business Server でお知らせを作成または削除する</span><span class="sxs-lookup"><span data-stu-id="b998b-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="b998b-126">Skype for Business Server で割り当てられていない番号範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="b998b-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="b998b-127">アナウンスの展開の確認</span><span class="sxs-lookup"><span data-stu-id="b998b-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="b998b-128">アナウンスを聞いてテストし、構成が予想どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b998b-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="b998b-129">省略Skype for Business でのアナウンスメントの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="b998b-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

