---
title: Skype for Business Server でオフライン インスタント メッセージング (IM) を有効または無効にする
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
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Skype for Business Server でオフライン インスタント メッセージング (IM) を有効または無効にする方法について説明します。
ms.openlocfilehash: 510ebe65e60b9ea12d2f368b0e2d33c705b8d0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801947"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="2204a-103">Skype for Business Server でオフライン インスタント メッセージング (IM) を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="2204a-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="2204a-104">Skype for Business Server でオフライン インスタント メッセージング (IM) を有効または無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2204a-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="2204a-105">Skype for Business Server でオフライン インスタント メッセージング (IM) を有効にする</span><span class="sxs-lookup"><span data-stu-id="2204a-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="2204a-106">オフライン IM は、Skype for Business クライアント (2016 C2R ビルド 16.0.6701.1000 以上) に組み込みのクライアント側機能で、Exchange Web サービス (EWS) を利用して Skype for Business クライアントからユーザーの Exchange メールボックスにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="2204a-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="2204a-107">オフライン IM は、Exchange Web サービス (EWS) を使用して、Skype for Business クライアントから受信者のメールボックスにオフライン メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="2204a-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="2204a-108">オフライン メッセージを送信するには、Skype for Business クライアントが EWS を使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2204a-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="2204a-109">インスタント メッセージングとプレゼンスの計画の詳細については、「Skype for Business Server でインスタント メッセージングとプレゼンスを計画する」 [を参照してください](../../plan-your-deployment/instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="2204a-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2204a-110">ユーザーのメールボックスが Exchange オンプレミスでホストされている場合は、Skype for Business クライアント (2016 C2R ビルド 16.0.6920.1000) が必要です。</span><span class="sxs-lookup"><span data-stu-id="2204a-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="2204a-111">Skype for Business Server でオフライン IM を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="2204a-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="2204a-112">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2204a-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="2204a-113">オフライン IM を有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2204a-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="2204a-114">Skype for Business Server 2015 CU3 では、EnableOfflineIM オプションは既定で $Trueに設定されています。</span><span class="sxs-lookup"><span data-stu-id="2204a-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="2204a-115">無効にするには、この値を無効に$False。</span><span class="sxs-lookup"><span data-stu-id="2204a-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="2204a-116">次のコマンドを実行して、オフライン IM を保存する機能が設定されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="2204a-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="2204a-117">オフライン IM と Exchange の統合</span><span class="sxs-lookup"><span data-stu-id="2204a-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="2204a-118">会話履歴フォルダーへのオフライン メッセージの自動保存を無効にするクライアント ポリシーがある場合、送信者はオフライン IM を使用できません (EnableIMAutoArchiving = $false)。</span><span class="sxs-lookup"><span data-stu-id="2204a-118">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false).</span></span> <span data-ttu-id="2204a-119">受信者がオフライン メッセージを受信できるのか確認するメカニズムはありません。</span><span class="sxs-lookup"><span data-stu-id="2204a-119">There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="2204a-120">同じ組織内で送信されたオフライン メッセージの場合、IM.Note.MissedConversation のメッセージ クラスを含む電子メール メッセージとして受信され、Outlook の [Missed **Conversation]** フォルダーに含まれるだけでなく、Skype for Business クライアントの最近のリスト/会話履歴タブで選択される会話履歴にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="2204a-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="2204a-121">フェデレーション組織から送信されたオフライン メッセージの場合、IM.Note.MisssedConversation を使用せずに電子メール メッセージとして受信され、見つからない会話または会話履歴フォルダーでは取得されません。</span><span class="sxs-lookup"><span data-stu-id="2204a-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="2204a-122">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2204a-122">Troubleshooting</span></span>

<span data-ttu-id="2204a-123">オフライン メッセージが受信され処理された場合から 2 分間のタイマーがあります。</span><span class="sxs-lookup"><span data-stu-id="2204a-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="2204a-124">オフライン メッセージを処理できない場合は、次のディレクトリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2204a-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="2204a-125">プライマリ Skype for Business ETL ログには、オフライン メッセージ処理に関する情報が含まれます。これは、調査/トラブルシューティングに最適なソースです。</span><span class="sxs-lookup"><span data-stu-id="2204a-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2204a-126">オフライン メッセージの送信に失敗し、[下書き] フォルダーにメッセージが格納されているという問題が報告されています。</span><span class="sxs-lookup"><span data-stu-id="2204a-126">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages.</span></span> <span data-ttu-id="2204a-127">これは、Exchange オンプレミス メールボックスで発生しました。</span><span class="sxs-lookup"><span data-stu-id="2204a-127">This occurred with Exchange On-Premises mailboxes.</span></span> <span data-ttu-id="2204a-128">この問題は、2016 年 6 月 14 日現在、すべての C2R チャネルで修正されています。</span><span class="sxs-lookup"><span data-stu-id="2204a-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
