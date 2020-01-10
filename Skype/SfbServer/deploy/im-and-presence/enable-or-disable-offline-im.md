---
title: Skype for Business Server でオフラインインスタントメッセージング (IM) を有効または無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Skype for Business Server でオフラインインスタントメッセージング (IM) を有効または無効にする方法について説明します。
ms.openlocfilehash: 02056618aff8a2dcaa6edc2023b67ad38aa9f314
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003047"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="c021f-103">Skype for Business Server でオフラインインスタントメッセージング (IM) を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="c021f-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="c021f-104">Skype for Business Server でオフラインインスタントメッセージング (IM) を有効または無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c021f-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="c021f-105">Skype for Business Server でオフラインインスタントメッセージング (IM) を有効にする</span><span class="sxs-lookup"><span data-stu-id="c021f-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="c021f-106">オフライン IM は、Exchange Web Services (EWS) を利用して、Skype for business クライアントからユーザーの Exchange メールボックスにメッセージを送信する、Skype for Business クライアント (2016 C2R build 16.0.6701.1000 以降) に組み込まれているクライアント側の機能です。</span><span class="sxs-lookup"><span data-stu-id="c021f-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="c021f-107">オフライン IM では、Exchange Web Services (EWS) を使って、Skype for Business クライアントから受信者のメールボックスにオフラインメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="c021f-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="c021f-108">オフラインメッセージを送信するには、EWS を Skype for Business クライアントで利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c021f-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="c021f-109">インスタントメッセージとプレゼンスの計画の詳細については、「 [Skype For Business Server でインスタントメッセージングとプレゼンスの計画を立てる](../../plan-your-deployment/instant-messaging-and-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c021f-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c021f-110">ユーザーのメールボックスが Exchange On-premises でホストされている場合は、Skype for Business クライアント (2016 C2R build 16.0.6920.1000) が必要です。</span><span class="sxs-lookup"><span data-stu-id="c021f-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="c021f-111">Skype for Business Server でオフライン IM を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="c021f-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="c021f-112">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c021f-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="c021f-113">以下のコマンドを実行して、オフライン IM を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c021f-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="c021f-114">Skype for Business Server 2015 CU3 以降ででは、EnableOfflineIM オプションが既定で $True に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c021f-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="c021f-115">無効にするには、この値を [$False] に設定します。</span><span class="sxs-lookup"><span data-stu-id="c021f-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="c021f-116">オフライン IM の保存機能が設定されていることを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c021f-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="c021f-117">オフライン IM と Exchange の統合</span><span class="sxs-lookup"><span data-stu-id="c021f-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="c021f-p103">送信者は、会話履歴フォルダー (EnableIMAutoArchiving = $false) へのオフライン メッセージの自動保存を無効にするクライアント ポリシーがある場合、オフライン IM を使用できません。受信者がオフライン メッセージを受信できるかどうかを確認するメカニズムはありません。</span><span class="sxs-lookup"><span data-stu-id="c021f-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="c021f-120">同じ組織内で送信されたオフラインメッセージについては、IM のメッセージクラスを含むメールメッセージとして受信されます。MissedConversation は、Outlook の**不在着信会話**フォルダーに含まれ、Skype for business クライアントの [最近のリスト] と [会話履歴] タブで選択された会話履歴も含まれます。</span><span class="sxs-lookup"><span data-stu-id="c021f-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="c021f-121">フェデレーション組織から送信されたオフライン メッセージの場合は、IM.Note.MisssedConversation を持たない電子メール メッセージとして配信され、[不在着信した会話] フォルダーや [会話履歴] フォルダーには入りません。</span><span class="sxs-lookup"><span data-stu-id="c021f-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="c021f-122">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c021f-122">Troubleshooting</span></span>

<span data-ttu-id="c021f-123">オフラインメッセージの受信時と処理時の間には、2分間のタイマーがあります。</span><span class="sxs-lookup"><span data-stu-id="c021f-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="c021f-124">オフラインメッセージが処理できない場合は、次のディレクトリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c021f-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="c021f-125">Skype for Business のプライマリ ETL ログには、オフラインメッセージ処理に関する情報が含まれており、調査/トラブルシューティングのための最適なソースとなります。</span><span class="sxs-lookup"><span data-stu-id="c021f-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c021f-p105">オフライン メッセージが送信に失敗して [下書き] フォルダーがメッセージでいっぱいになったという問題が報告されています。これは、Exchange On-Premises のメールボックスで発生します。この問題は、2016 年 6 月 14 日の時点ですべての C2R チャネルで修正されました。 </span><span class="sxs-lookup"><span data-stu-id="c021f-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
