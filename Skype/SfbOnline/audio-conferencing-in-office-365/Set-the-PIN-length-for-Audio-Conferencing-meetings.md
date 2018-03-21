---
title: "オーディオ会議の会議の暗証番号 (pin) の長さを設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "パラメーターの長さと、PIN の要件を説明し、ビジネスの Skype での会議の長さを設定する方法を参照してください。"
ms.openlocfilehash: 308bce9196f085c1f9473e74746bccd2f0ca96c5
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>オーディオ会議の会議の暗証番号 (pin) の長さを設定します。

設定するオーディオの会議で Skype の企業またはマイクロソフトのチームのときに、オーディオ会議ブリッジが表示されます。 会議用ブリッジは、1 つまたは複数の電話番号を含めることができます。 設定した電話番号はビジネスおよびマイクロソフトのチームのアプリケーションの Skype の会議の招待に含まれます。
  
オーディオ会議ブリッジ、電話を使用して会議にダイヤルインしている人のための呼び出しに応答します。 自動応答から、設定によっては、音声メッセージを呼び出し元に応答、通知を再生でき、自分の名前を記録するための呼び出し元に問い合わせてください。 **マイクロソフト ブリッジの設定**では、会議の通知の設定を変更することができ、会議の参加、会議の開催者によって使用されているピンの長さを設定します。 ミーティングの開催者は、ビジネスまたはマイクロソフトのチームのアプリケーションに、Skype を使用してミーティングに参加することはできない場合は、会議を開始するためのピンを使用します。
  
## <a name="setting-the-pin-length"></a>暗証番号 (pin) の長さを設定

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Sign in to Office 365 with your work or school account.
    
3. 既定値は 5 です。
    
4. [**セキュリティ]** > **暗証番号 (pin) の長さ**を選択し、PIN の桁数を選択し、[**保存**] をクリックします。
    
> [!NOTE]
> PIN とは異なる、会議の id です。 会議 Id は、ミーティングに参加するときに、呼び出し元が使用されます。 ミーティングに使用されます。 暗証番号 (pin) を使用して、会議の開催者は、呼び出し元を認証します。 
  
## <a name="want-to-know-more-about-pin-settings"></a>暗証番号 (pin) の設定の詳細を知りたいとしていますか。

- ピンすることが 4 から 12 桁の数字です。デフォルトは 5 です。 番号は、ピンを作成するときにのみ使用されます。 文字と特殊文字は使用されません。
    
- 暗証番号 (pin) にのみ必要な場合、Skype ビジネスまたはマイクロソフトのチームのユーザーの会議の開催者に会議が開始されていない既に。 場合はすべてのユーザーがダイヤルイン会議、PIN は、会議の開催者、会議を開始するために必要。
    
- 暗証番号 (pin) のセキュリティ設定は、すべての Microsoft のブリッジに関連付けられている電話番号に適用されます。 各ブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Go to the Office 365 admin centerSkype for Business.

- 時間を短縮または、これを自動化するには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用することができます。
    
- 8 PIN の桁数を設定します。`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 
    
  - Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
  
## <a name="see-also"></a>関連項目

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)

