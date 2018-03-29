---
title: Skype for Business Server 2015 でのオフライン インスタント メッセージング (IM) の有効化または無効化
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 有効にするか、ビジネス サーバー 2015 のオフライン インスタント メッセージング (IM) では、Skype を無効にするについて説明します。
ms.openlocfilehash: a9133ad82e4d25fae2aebd266273ecbb37c2a010
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a><span data-ttu-id="0bcdd-103">Skype for Business Server 2015 でのオフライン インスタント メッセージング (IM) の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="0bcdd-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0bcdd-104">有効にするか、ビジネス サーバー 2015 のオフライン インスタント メッセージング (IM) では、Skype を無効にするについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server 2015.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a><span data-ttu-id="0bcdd-105">ビジネス サーバー 2015 の Skype でオフライン インスタント メッセージング (IM) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-105">Enable Offline Instant Messaging (IM) in Skype for Business Server 2015</span></span>

<span data-ttu-id="0bcdd-106">オフライン IM は、ビジネスのクライアントは、Skype に組み込まれたクライアント側の機能 (2016 C2R 16.0.6701.1000 をビルドするまたはそれ以上)、Skype のビジネス クライアントからユーザーの Exchange メールボックスにメッセージを送信するように、Exchange Web サービス (EWS) を活用します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="0bcdd-107">オフライン IM では、Exchange Web サービス (EWS) を使用して、ビジネス クライアント用の Skype から受信者のメールボックスにオフライン メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="0bcdd-108">EWS はオフライン メッセージを送信するためのビジネス クライアント用の Skype を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="0bcdd-109">インスタント メッセージングとプレゼンスの計画の詳細については、[インスタント メッセージングとプレゼンスのビジネス サーバー 2015 Skype での計画](../../plan-your-deployment/instant-messaging-and-presence.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server 2015](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0bcdd-110">(2016 C2R は、16.0.6920.1000 を構築)、ビジネス クライアント用の Skype が必要なユーザーのメールボックスで Exchange を社内設置型のホストが場合、</span><span class="sxs-lookup"><span data-stu-id="0bcdd-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server-2015-with-cu3"></a><span data-ttu-id="0bcdd-111">CU3 のビジネス サーバーの 2015 の Skype で IM オフラインを無効にするを有効または</span><span class="sxs-lookup"><span data-stu-id="0bcdd-111">To enable or disable Offline IM in Skype for Business Server 2015 with CU3</span></span>

1. <span data-ttu-id="0bcdd-112">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="0bcdd-113">以下のコマンドを実行して、オフライン IM を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-113">Run the following command to enable Offline IM.</span></span>
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="0bcdd-114">ビジネス サーバー 2015 CU3 の Skype は、EnableOfflineIM オプションは、既定で $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="0bcdd-115">無効にするには、この値を $False に設定します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="0bcdd-116">オフライン IM を保存する機能の設定を確認するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="0bcdd-117">オフライン IM と Exchange の統合</span><span class="sxs-lookup"><span data-stu-id="0bcdd-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="0bcdd-p103">送信者は、会話履歴フォルダー (EnableIMAutoArchiving = $false) へのオフライン メッセージの自動保存を無効にするクライアント ポリシーがある場合、オフライン IM を使用できません。受信者がオフライン メッセージを受信できるかどうかを確認するメカニズムはありません。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="0bcdd-120">オフラインのメッセージを同じ組織内で送信されるは、それらは IM のメッセージ クラスを持つ電子メール メッセージとして受信されます。Note.MissedConversation を集荷する最近使用したリストと会話履歴] タブには、Skype のビジネス クライアントの会話の履歴と同様に、Outlook の**会話の失敗**フォルダーに含まれるとします。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="0bcdd-121">フェデレーション組織から送信されたオフライン メッセージの場合は、IM.Note.MisssedConversation を持たない電子メール メッセージとして配信され、[不在着信した会話] フォルダーや [会話履歴] フォルダーには入りません。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="0bcdd-122">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0bcdd-122">Troubleshooting</span></span>

<span data-ttu-id="0bcdd-123">オフライン メッセージがピックアップして処理するときの 2 分のタイマーがあります。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="0bcdd-124">オフライン メッセージを処理できない場合は、次のディレクトリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
   ```
  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler
  ```

<span data-ttu-id="0bcdd-125">ビジネス ETL ログの主な Skype はオフライン メッセージの処理に関する情報が含まれます、調査とトラブルシューティングのため、最適な情報源です。</span><span class="sxs-lookup"><span data-stu-id="0bcdd-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0bcdd-p105">オフライン メッセージが送信に失敗して [下書き] フォルダーがメッセージでいっぱいになったという問題が報告されています。これは、Exchange On-Premises のメールボックスで発生します。この問題は、2016 年 6 月 14 日の時点ですべての C2R チャネルで修正されました。 </span><span class="sxs-lookup"><span data-stu-id="0bcdd-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span> 
  

