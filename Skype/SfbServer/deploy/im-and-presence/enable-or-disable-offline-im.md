---
title: '[オフライン インスタント メッセージング (IM) を有効または無効にする] Skype for Business Server'
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
description: オフライン インスタント メッセージング (IM) を有効または無効にする方法については、Skype for Business Server。
ms.openlocfilehash: ba9045f0e161b4056142fc69528a4f1e7c01a11637c1bff42ec7cc14fe7610a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294864"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>[オフライン インスタント メッセージング (IM) を有効または無効にする] Skype for Business Server
 
オフライン インスタント メッセージング (IM) を有効または無効にする方法については、Skype for Business Server。
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>[オフライン インスタント メッセージング (IM) を有効にする] Skype for Business Server

オフライン IM は、Skype for Business クライアント (2016 C2R ビルド 16.0.6701.1000 以上) に組み込むクライアント側の機能で、Exchange Web サービス (EWS) を利用して Skype for Business クライアントからユーザーの Exchange メールボックスにメッセージを送信します。 オフライン IM は、Exchange Web サービス (EWS) を使用して、クライアントから受信者Skype for Businessにオフライン メッセージを送信します。 オフライン メッセージを送信するには、Skype for Businessクライアントで EWS を使用できる必要があります。 インスタント メッセージングとプレゼンスの計画の詳細については、「Plan [for instant Messaging and presence in](../../plan-your-deployment/instant-messaging-and-presence.md)Skype for Business Server」 を参照してください。
  
> [!NOTE]
> ユーザーのメールボックスが Exchange オンプレミスでホストされている場合、Skype for Business クライアント (2016 C2R ビルド 16.0.6920.1000) が必要です 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>オフライン IM を有効または無効にするには、Skype for Business Server

1. 管理シェルSkype for Business Server開きます。
    
2. オフライン IM を有効にするには、次のコマンドを実行します。
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > 2015 Skype for Business Server CU3 では、EnableOfflineIM オプションは既定で$True設定されています。 無効にするには、この値を [$False] に設定します。 
  
3. 次のコマンドを実行して、オフライン IM を保存する機能が設定されているのを確認します。
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>オフライン IM 統合とExchange

オフライン IM は、会話履歴フォルダー (EnableIMAutoArchiving = $false) へのオフライン メッセージの自動保存を無効にするクライアント ポリシーを持っている場合、送信者は使用できません。 受信者がオフライン メッセージを受信できるのか確認するメカニズムはありません。
  
同じ組織内で送信されたオフライン メッセージの場合、IM.Note.MissedConversation のメッセージ クラスを含む電子メール メッセージとして受信され、Outlookの [会話の欠落] フォルダーに含まれるだけでなく、Skype for Business クライアントの [最近のリスト/会話履歴] タブで取得される会話履歴にも含まれます。
  
フェデレーション組織から送信されたオフライン メッセージの場合、IM.Note.MisssedConversation なしで電子メール メッセージとして受信され、欠落した会話や会話の履歴フォルダーでは取得されません。 
  
## <a name="troubleshooting"></a>トラブルシューティング

オフライン メッセージが受信され、処理された時から 2 分間のタイマーがあります。 オフライン メッセージを処理できない場合は、次のディレクトリに表示されます。 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

ETL ログSkype for Businessには、オフライン メッセージ処理に関する情報が含まれるので、調査やトラブルシューティングに最適なソースです。 
  
> [!NOTE]
> オフライン メッセージの送信に失敗し、[下書き] フォルダーにメッセージが入力されている問題が報告されています。 これは、オンプレミスExchangeで発生しました。 この問題は、2016 年 6 月 14 日現在のすべての C2R チャネルで修正されています。  
