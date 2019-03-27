---
title: 有効にするか、ビジネスのサーバーのオフライン インスタント メッセージング (IM) では、Skype を無効にします。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 有効にするか、ビジネスのサーバーのオフライン インスタント メッセージング (IM) では、Skype を無効にするについて説明します。
ms.openlocfilehash: 29342f3903e58f90ab4d2a939be6cd20d3f8e31b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899187"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>有効にするか、ビジネスのサーバーのオフライン インスタント メッセージング (IM) では、Skype を無効にします。
 
有効にするか、ビジネスのサーバーのオフライン インスタント メッセージング (IM) では、Skype を無効にするについて説明します。
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>ビジネス サーバーのオフライン インスタント メッセージング (IM) では、Skype を有効にします。

オフライン IM は、ビジネスのクライアントは、Skype に組み込まれたクライアント側の機能 (2016 C2R 16.0.6701.1000 をビルドするまたはそれ以上)、Skype のビジネス クライアントからユーザーの Exchange メールボックスにメッセージを送信するように、Exchange Web サービス (EWS) を活用します。 オフライン IM では、Exchange Web サービス (EWS) を使用して、ビジネス クライアント用の Skype から受信者のメールボックスにオフライン メッセージを送信します。 EWS はオフライン メッセージを送信するためのビジネス クライアント用の Skype を使用する必要があります。 インスタント メッセージングとプレゼンスの計画の詳細については、[インスタント メッセージングとプレゼンス ビジネス サーバーの Skype での計画](../../plan-your-deployment/instant-messaging-and-presence.md)を参照してください。
  
> [!NOTE]
> (2016 C2R は、16.0.6920.1000 を構築)、ビジネス クライアント用の Skype が必要なユーザーのメールボックスで Exchange を社内設置型のホストが場合、 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>ビジネス サーバーの Skype で IM オフラインを無効にするを有効または

1. Skype をビジネス サーバー管理シェルを開きます。
    
2. 以下のコマンドを実行して、オフライン IM を有効にします。
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > ビジネス サーバー 2015 CU3 の Skype は、EnableOfflineIM オプションは、既定で $True に設定します。 無効にするには、この値を $False に設定します。 
  
3. オフライン IM を保存する機能の設定を確認するのには次のコマンドを実行します。
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>オフライン IM と Exchange の統合

送信者は、会話履歴フォルダー (EnableIMAutoArchiving = $false) へのオフライン メッセージの自動保存を無効にするクライアント ポリシーがある場合、オフライン IM を使用できません。受信者がオフライン メッセージを受信できるかどうかを確認するメカニズムはありません。
  
オフラインのメッセージを同じ組織内で送信されるは、それらは IM のメッセージ クラスを持つ電子メール メッセージとして受信されます。Note.MissedConversation を集荷する最近使用したリストと会話履歴] タブには、Skype のビジネス クライアントの会話の履歴と同様に、Outlook の**会話の失敗**フォルダーに含まれるとします。
  
フェデレーション組織から送信されたオフライン メッセージの場合は、IM.Note.MisssedConversation を持たない電子メール メッセージとして配信され、[不在着信した会話] フォルダーや [会話履歴] フォルダーには入りません。 
  
## <a name="troubleshooting"></a>トラブルシューティング

オフライン メッセージがピックアップして処理するときの 2 分のタイマーがあります。 オフライン メッセージを処理できない場合は、次のディレクトリに表示されます。 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

ビジネス ETL ログの主な Skype はオフライン メッセージの処理に関する情報が含まれます、調査とトラブルシューティングのため、最適な情報源です。 
  
> [!NOTE]
> オフライン メッセージが送信に失敗して [下書き] フォルダーがメッセージでいっぱいになったという問題が報告されています。これは、Exchange On-Premises のメールボックスで発生します。この問題は、2016 年 6 月 14 日の時点ですべての C2R チャネルで修正されました。   
