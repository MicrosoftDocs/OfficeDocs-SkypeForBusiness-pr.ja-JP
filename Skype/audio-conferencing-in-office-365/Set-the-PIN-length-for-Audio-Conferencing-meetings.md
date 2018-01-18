---
title: "オーディオ会議の会議の暗証番号 (pin) の長さを設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "パラメーターの長さと、PIN の要件を説明し、ビジネスの Skype での会議の長さを設定する方法を参照してください。"
ms.openlocfilehash: 853a8ed74377dd76b38eab62b04fc75e3295df2d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>オーディオ会議の会議の暗証番号 (pin) の長さを設定します。

設定するオーディオの会議で Skype の企業またはマイクロソフトのチームのときに、オーディオ会議ブリッジが表示されます。 会議用ブリッジは、1 つまたは複数の電話番号を含めることができます。 設定した電話番号はビジネスおよびマイクロソフトのチームのアプリケーションの Skype の会議の招待に含まれます。
  
オーディオ会議ブリッジ、電話を使用して会議にダイヤルインしている人のための呼び出しに応答します。 自動応答から、設定によっては、音声メッセージを呼び出し元に応答、通知を再生でき、自分の名前を記録するための呼び出し元に問い合わせてください。 **マイクロソフト ブリッジの設定**では、会議の通知の設定を変更することができ、会議の参加、会議の開催者によって使用されているピンの長さを設定します。 ミーティングの開催者は、ビジネスまたはマイクロソフトのチームのアプリケーションに、Skype を使用してミーティングに参加することはできない場合は、会議を開始するためのピンを使用します。
  
## <a name="setting-the-pin-length"></a>暗証番号 (pin) の長さを設定

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **Microsoft ブリッジ設定**します。
    
4. [**セキュリティ]** > **暗証番号 (pin) の長さ**を選択し、PIN の桁数を選択し、[**保存**] をクリックします。
    
> [!NOTE]
> PIN とは異なる、会議の id です。 会議 Id は、ミーティングに参加するときに、呼び出し元が使用されます。 ミーティングに使用されます。 暗証番号 (pin) を使用して、会議の開催者は、呼び出し元を認証します。 
  
## <a name="want-to-know-more-about-pin-settings"></a>暗証番号 (pin) の設定の詳細を知りたいとしていますか。

- ピンすることが 4 から 12 桁の数字です。デフォルトは 5 です。 番号は、ピンを作成するときにのみ使用されます。 文字と特殊文字は使用されません。
    
- 暗証番号 (pin) にのみ必要な場合、Skype ビジネスまたはマイクロソフトのチームのユーザーの会議の開催者に会議が開始されていない既に。 場合はすべてのユーザーがダイヤルイン会議、PIN は、会議の開催者、会議を開始するために必要。
    
- 暗証番号 (pin) のセキュリティ設定は、すべての Microsoft のブリッジに関連付けられている電話番号に適用されます。 各ブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を短縮または、これを自動化するには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用することができます。
    
- 8 PIN の桁数を設定します。`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。 Windows PowerShell を実行する複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 を管理できます。 Windows PowerShell を使い始めるには、以下のトピックを参照してください。
    
  - [Office 365 の PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。 次のトピックで、これらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
  
## <a name="see-also"></a>関連項目

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)

