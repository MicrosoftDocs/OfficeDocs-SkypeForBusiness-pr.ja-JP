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
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Skype for Business Server でオフラインインスタントメッセージング (IM) を有効または無効にする
 
Skype for Business Server でオフラインインスタントメッセージング (IM) を有効または無効にする方法について説明します。
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Skype for Business Server でオフラインインスタントメッセージング (IM) を有効にする

オフライン IM は、Exchange Web Services (EWS) を利用して、Skype for business クライアントからユーザーの Exchange メールボックスにメッセージを送信する、Skype for Business クライアント (2016 C2R build 16.0.6701.1000 以降) に組み込まれているクライアント側の機能です。 オフライン IM では、Exchange Web Services (EWS) を使って、Skype for Business クライアントから受信者のメールボックスにオフラインメッセージが送信されます。 オフラインメッセージを送信するには、EWS を Skype for Business クライアントで利用できるようにする必要があります。 インスタントメッセージとプレゼンスの計画の詳細については、「 [Skype For Business Server でインスタントメッセージングとプレゼンスの計画を立てる](../../plan-your-deployment/instant-messaging-and-presence.md)」を参照してください。
  
> [!NOTE]
> ユーザーのメールボックスが Exchange On-premises でホストされている場合は、Skype for Business クライアント (2016 C2R build 16.0.6920.1000) が必要です。 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Skype for Business Server でオフライン IM を有効または無効にするには

1. Skype for Business Server 管理シェルを開きます。
    
2. 以下のコマンドを実行して、オフライン IM を有効にします。
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > Skype for Business Server 2015 CU3 以降ででは、EnableOfflineIM オプションが既定で $True に設定されています。 無効にするには、この値を [$False] に設定します。 
  
3. オフライン IM の保存機能が設定されていることを確認するには、次のコマンドを実行します。
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>オフライン IM と Exchange の統合

送信者は、会話履歴フォルダー (EnableIMAutoArchiving = $false) へのオフライン メッセージの自動保存を無効にするクライアント ポリシーがある場合、オフライン IM を使用できません。受信者がオフライン メッセージを受信できるかどうかを確認するメカニズムはありません。
  
同じ組織内で送信されたオフラインメッセージについては、IM のメッセージクラスを含むメールメッセージとして受信されます。MissedConversation は、Outlook の**不在着信会話**フォルダーに含まれ、Skype for business クライアントの [最近のリスト] と [会話履歴] タブで選択された会話履歴も含まれます。
  
フェデレーション組織から送信されたオフライン メッセージの場合は、IM.Note.MisssedConversation を持たない電子メール メッセージとして配信され、[不在着信した会話] フォルダーや [会話履歴] フォルダーには入りません。 
  
## <a name="troubleshooting"></a>トラブルシューティング

オフラインメッセージの受信時と処理時の間には、2分間のタイマーがあります。 オフラインメッセージが処理できない場合は、次のディレクトリに表示されます。 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Skype for Business のプライマリ ETL ログには、オフラインメッセージ処理に関する情報が含まれており、調査/トラブルシューティングのための最適なソースとなります。 
  
> [!NOTE]
> オフライン メッセージが送信に失敗して [下書き] フォルダーがメッセージでいっぱいになったという問題が報告されています。これは、Exchange On-Premises のメールボックスで発生します。この問題は、2016 年 6 月 14 日の時点ですべての C2R チャネルで修正されました。   
