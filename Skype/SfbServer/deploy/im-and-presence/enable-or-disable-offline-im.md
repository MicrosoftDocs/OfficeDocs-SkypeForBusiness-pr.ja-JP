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
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Skype for Business Server でオフライン インスタント メッセージング (IM) を有効または無効にする
 
Skype for Business Server でオフライン インスタント メッセージング (IM) を有効または無効にする方法について説明します。
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Skype for Business Server でオフライン インスタント メッセージング (IM) を有効にする

オフライン IM は、Skype for Business クライアント (2016 C2R ビルド 16.0.6701.1000 以上) に組み込みのクライアント側機能で、Exchange Web サービス (EWS) を利用して Skype for Business クライアントからユーザーの Exchange メールボックスにメッセージを送信します。 オフライン IM は、Exchange Web サービス (EWS) を使用して、Skype for Business クライアントから受信者のメールボックスにオフライン メッセージを送信します。 オフライン メッセージを送信するには、Skype for Business クライアントが EWS を使用できる必要があります。 インスタント メッセージングとプレゼンスの計画の詳細については、「Skype for Business Server でインスタント メッセージングとプレゼンスを計画する」 [を参照してください](../../plan-your-deployment/instant-messaging-and-presence.md)。
  
> [!NOTE]
> ユーザーのメールボックスが Exchange オンプレミスでホストされている場合は、Skype for Business クライアント (2016 C2R ビルド 16.0.6920.1000) が必要です。 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Skype for Business Server でオフライン IM を有効または無効にするには

1. Skype for Business Server 管理シェルを開きます。
    
2. オフライン IM を有効にするには、次のコマンドを実行します。
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > Skype for Business Server 2015 CU3 では、EnableOfflineIM オプションは既定で $Trueに設定されています。 無効にするには、この値を無効に$False。 
  
3. 次のコマンドを実行して、オフライン IM を保存する機能が設定されているのを確認します。
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>オフライン IM と Exchange の統合

会話履歴フォルダーへのオフライン メッセージの自動保存を無効にするクライアント ポリシーがある場合、送信者はオフライン IM を使用できません (EnableIMAutoArchiving = $false)。 受信者がオフライン メッセージを受信できるのか確認するメカニズムはありません。
  
同じ組織内で送信されたオフライン メッセージの場合、IM.Note.MissedConversation のメッセージ クラスを含む電子メール メッセージとして受信され、Outlook の [Missed **Conversation]** フォルダーに含まれるだけでなく、Skype for Business クライアントの最近のリスト/会話履歴タブで選択される会話履歴にも含まれます。
  
フェデレーション組織から送信されたオフライン メッセージの場合、IM.Note.MisssedConversation を使用せずに電子メール メッセージとして受信され、見つからない会話または会話履歴フォルダーでは取得されません。 
  
## <a name="troubleshooting"></a>トラブルシューティング

オフライン メッセージが受信され処理された場合から 2 分間のタイマーがあります。 オフライン メッセージを処理できない場合は、次のディレクトリに表示されます。 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

プライマリ Skype for Business ETL ログには、オフライン メッセージ処理に関する情報が含まれます。これは、調査/トラブルシューティングに最適なソースです。 
  
> [!NOTE]
> オフライン メッセージの送信に失敗し、[下書き] フォルダーにメッセージが格納されているという問題が報告されています。 これは、Exchange オンプレミス メールボックスで発生しました。 この問題は、2016 年 6 月 14 日現在、すべての C2R チャネルで修正されています。  
