---
title: "組織のクレジットの通信を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
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
- Licensing
- Strat_SB_PSTN
description: "ユーザーや組織のライセンスの課金通信クレジット (PSTN 消費) を設定する方法について説明します。 "
ms.openlocfilehash: b2eb4616e9f79392558d421723ee013759a455fd
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-communications-credits-for-your-organization"></a>組織のクレジットの通信を設定します。

Skype for Business と Microsoft チーム フリー ダイヤルの番号を使用したい場合、クレジットの通信を設定する必要があります。また、ことを設定する通信クレジット (国内または国際) プランの呼び出しと電話会議の**すべての宛先**にダイヤルアウト機能を必要とするユーザーをお勧めします。多くの国/地域も含まれていますが、一部の宛先は、サブスクリプションの計画を呼び出す、または電話会議には含まれません。課金通信クレジットを設定して**の通信クレジット**のライセンスをユーザーに割り当てる考えて実行すると、組織の分を (、プランの呼び出し、または電話会議プランに応じて、国/地域で)、それらのユーザー通話の発信など、会議の音声会議から発信することはできません。読み、金額を資金調達推奨などの詳細をご[通信を加算したものは何ですか?](what-are-communications-credits.md)
  
> [!NOTE]
> 確認するに必要なコスト、[単価を以下を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a>手順 1: は、電話会議での呼び出しを計画するライセンスをユーザーに割り当てる

サインアップすると、住んでいる国/地域によって秒数を表示します。検索の国または地域を [ここ] が表示される時間を分単位で表示できます。(../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md))。その分を使用すると、通話は切断されます。これが発生しないようにするには、クレジットの通信を設定する必要があります。
  
ためには、ユーザーには**、電話会議または電話システムでのライセンスを割り当てる必要があります**。
  
- **電話会議**のライセンスをユーザーに割り当てます。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。
    
    このライセンスの割り当て後は、電話会議を設定する必要があります。ステップ バイ ステップの手順は、「 [Skype for Business とチームの Microsoft の音声会議をセットアップする](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)」を参照してください。
    
- ユーザーには、**電話システム**と、国内または国内/国際通話プランのライセンスを割り当てます。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。
    
    > [!NOTE]
    > 通信を加算したものは必要ありませんがまだも**国内通話プラン**または**国内と国際通話プラン**のライセンスを割り当てる必要があります。
  
    これらのライセンスの割り当て後、組織の電話番号を取得し、[これらの数値を組織のユーザーに割り当てる必要があります。詳しい手順については、[プランの呼び出しを設定する](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)を参照してください。
    
詳細については、 [Skype for Business や Microsoft チーム アドオンのライセンス](skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>手順 2: 組織のクレジットの通信を設定します。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. Office 365 管理センターの左のナビゲーションでは、**課金**に移動 > **サブスクリプション** > **アドオン** > **アドオンを購入**と**の通信を加算したもの**を選択し、 > **を今すぐ購入**します。
    
3. **通信クレジット**サブスクリプション] ページで、情報を入力し、[**次へ**] をクリックします。
    
  - **追加資金**自分のアカウントに追加する金額を入力します。しないを有効にした自動-充電、したら、これらの資金が不足している場合 (受信フリー ダイヤル サービス) などの通信を加算したものを使用して有効になっている機能の呼び出しが中断されます。残高が 0 (ゼロ) に到達するたびに、通信クレジット残高を手動で補給することを避けるため、自動回復機能を有効にすることをお勧めします。
    
  - **自動回復**残高が設定されているしきい値を下回るときに、自動回復を有効にする、自分のアカウントに自動的に補充します。
    
    **自動充電**設定を使用する必要がある、通信クレジット残高は 0 (ゼロ) に達するまでのサービス中断を回避することをお勧めします。送信されますメール (など、クレジット_カードの期限切れ)、充電トランザクションが失敗すると、[充電トランザクションが失敗して、通信クレジット残高が 0 (ゼロ) に達したとき。
    
  - **充電金額**トリガー金額を以下になると、自分のアカウントに追加する**と充電**] ボックスに入力します。
    
  - **トリガー金額**'*開始*' の自動回復するために使用される**残高を下回ると**] ボックスに入力します。後の残高がこの金額を下回る充電量が自分のアカウントに自動的に追加されます。

      > [!NOTE]
    > 資金がのみに適用するサービスが使用される場合、マイクロソフトの通信クレジットが単価を発行します。購入日の 12 か月以内未使用の資金が終了し、没収されます。 
    
4. 支払い情報を入力し、[**注文**] をクリックします。
    >[!IMPORTANT]
    >ボリューム ライセンス ユーザーの場合は、支払のエンタープライズ契約番号を選択することがあります。複数のエンタープライズ契約番号がある場合は、支払いに使用する企業契約を選択することができます。Enterprise 契約番号 (ある場合) と関連付ける発注書番号を指定するのには、営業案件を指定するもされます。
    
別の使用を計画する呼び出しの音量と率の考慮事項の各組織が表示されます。現在のサービス プロバイダーからこの種類の利用状況のデータを取得する必要があります。組織が既に Skype for Business Online 既にプロバイダーとして使用して、サービスが利用状況のデータを取得する**Skype for Business 管理センター**で確認して > **レポート** > **PSTN の使用方法の詳細**レポート。
  
クレジットの通信を設定する場合に、組織に必要な量を決定するの通話の使用状況を調べる必要があります。**PSTN の使用方法の詳細**レポートを確認して通話の使用状況に関する情報を取得できます。このレポートでは、記憶域のデータをエクスポートまたはカスタム レポートを作成する場合は、電話のデータ レコードを Excel にエクスポートできます。利用状況を表示するには、 [Skype for Business PSTN の使用状況レポート](../skype-for-business-online-reporting/pstn-usage-report.md)を参照してください。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>手順 3: ユーザーに連絡クレジット ライセンスを割り当てます。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. Office 365 管理センターの左のナビゲーションでの [**ユーザー**] に移動 > **アクティブなユーザー**の場合は、し、一覧からユーザーまたはユーザーを選択します。
    
3. 操作ウィンドウの [**製品のライセンス**] で、[**編集**] をクリックします。
    
4. [**製品のライセンス**] ページに切り替えます。 * * 通信クレジット * * するには、 **[**このライセンスを割り当てると、[**保存**] をクリックします。
    
    > [!NOTE]
    > 場合でも、**エンタープライズ E5**ライセンスが割り当てられているユーザーがある場合は、この操作をまだお勧めします。
  
## <a name="want-to-know-about-plans-and-pricing"></a>プランと価格を知りたいとしていますか。

[プランと価格を次のリンクのいずれかにアクセスする、確認できます。
  
- [通話プラン](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [電話会議の計画](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [電話システムの計画](https://go.microsoft.com/fwlink/?LinkId=799763)
    
[Office 365 管理センターにサインイン](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)することの情報を表示することもできます。**課金**にアクセスして > **サブスクリプション** > **追加サブスクリプション**します。
  
ライセンスが各機能に必要なライセンスとテーブルを表示するには、 [Skype for Business や Microsoft チーム アドオンのライセンス](skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。
  
## <a name="related-topics"></a>関連トピック

- [Skype for Business Online をセットアップします。](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
    
- [管理者のヘルプ - 電話システムでのボイス メールを設定します。](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)
    
- [プランの呼び出しを設定して](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)、 [Office 365 のプランの呼び出し](calling-plans-for-office-365.md)
    
- [金を追加およびクレジットの通信を管理します。](add-funds-and-manage-communications-credits.md)
    
- [クラウド コネクタを構成して](https://technet.microsoft.com/en-us/library/mt605228.aspx)、[クラウド コネクタのダウンロード](https://aka.ms/CloudConnectorInstaller)
