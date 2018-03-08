---
title: "電話会議ブリッジの設定を変更します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: "発信者に応答メッセージを表示して、for Business のクライアント Skype これらを使っていない場合は、名前との会議の開催者 pin を収集するに使用する Microsoft ダイヤルイン会議ブリッジの設定を変更するのには必要な手順を取得します。 "
ms.openlocfilehash: f37af15b4ab66eb5765cccbdba63b3bb6bb14597
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>電話会議ブリッジの設定を変更します。

Office 365 での電話会議をセットアップするときに、電話会議ブリッジと呼ばれるからユーザーの電話番号が表示されます。会議ブリッジには、1 つ以上の電話番号を含めることができます。これらの電話番号は、発信者が会議にダイヤルインするときに使用されます。電話番号が、Skype for Business または Microsoft チーム会議の出席依頼の下部に含まれています。
  
会議ブリッジが呼び出しに応答と会議の自動応答、し、自分の設定によっての使用を促すボイス メッセージと発信者のプロンプトをできます通知を再生、発信者相手の名前を記録するように依頼し PIN の設定を制御します。Pin ができるようにするために、会議の開催者与えられる会議を開始する場合を使っていない Skype for Business または Microsoft チーム アプリです。

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>電話会議ブリッジの設定を変更します。

 **発信者が会議に参加するときに、会議のエクスペリエンスを設定します。**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**で、左のナビゲーションで移動**電話会議**に > **Microsoft ブリッジの設定**します。
    
4. [ **Microsoft bridge の設定**] ページで、[**会議参加エクスペリエンス**を選択します。
    
  - **会議のエントリを有効にして終了通知を有効にするには**これが既定で選択されます。チェック ボックスをオフにする場合は、入力したり、会議のまま、会議に参加しているユーザーが通知されません。
    
    **会議のエントリを有効にして終了通知を有効にする**] を選択するときに、**開始/終了のお知らせの種類**] の一覧からこれらのオプションを選択できます。
    
  - **名前や電話番号**ユーザーが会議にダイヤルインするときに参加するときに、電話番号が再生されます。
    
  - **トーン**ユーザーが会議にダイヤルインするときに参加するときにオーディオのトーンが再生されます。
    
    > [!NOTE]
    > プレビュー機能とすべての顧客に現時点でのお知らせの種類に**音**を使用してはします。
  
  - **質問の発信者**これが既定で選択されます。チェック ボックスをオフにする場合、発信者が、会議に参加する前に、相手の名前を記録するように依頼されません。
    
5. 変更が終了したら、[**保存**] をクリックします。
    
**会議の PIN の長さを設定します。**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。
    
4. **Microsoft ブリッジの設定**] ページで、[**セキュリティ**]、[ **PIN の長さ**] ボックスの一覧で、[PIN の桁数を入力し、[**保存**] をクリックします。
    
    > [!IMPORTANT]
    > 4、12 桁の数字の間、暗証番号 (pin) があります。 
  
**ユーザーにメールを送信するかどうかを選択します。**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。
    
4. [ **Microsoft bridge の設定**] ページで、選択や**、電話会議の設定を変更した場合、ユーザーにメールを自動的に送信**] をオフにし、[**保存**] をクリックします。
    
    詳細については[、電話会議の設定を変更する場合にユーザーにメールが自動的に送信](emails-sent-to-users-when-their-settings-change.md)を参照してください。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- 時刻を保存するか、このプロセスを自動化に、[セット CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 )コマンドレットを使用することができます。
    
- Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)

