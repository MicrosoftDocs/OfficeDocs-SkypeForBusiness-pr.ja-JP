---
title: 組織のために通信クレジットをセットアップする
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: afe1ce61a5c5f137b5123cb530094d6a651ecf7f
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30541785"
---
# <a name="set-up-communications-credits-for-your-organization"></a>組織のために通信クレジットをセットアップする

[] Skype for Business および Microsoft Teams で無料電話番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。 また、 **任意の発信先** にダイヤルアウトする機能が必要な、通話プラン (国内および国際通話) ユーザーと電話会議ユーザー向けにコミュニケーション クレジットを設定することをお勧めします。 ご利用の通話プランまたは電話会議のサブスクリプションでは、多くの国や地域が含まれていますが、一部の発信先が含まれていない可能性があります。 コミュニケーション クレジットの請求を設定しない場合や、ユーザーに **コミュニケーション クレジット**のライセンスを割り当てない場合に (国/地域の通話プランまたは電話会議プランに基づき) 組織の通話分数が不足すると、これらのユーザーは通話を発信することや、電話会議からダイヤルアウトすることができなくなります。 読み取ることによって資金調達の金額は、推奨などの詳細を取得することができます、[通信のクレジットは何ですか?](what-are-communications-credits.md)
  
> [!NOTE]
> 費用を確認するには、[こちらで料金をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a>手順 1: 電話会議と通話プランのライセンスをユーザーに割り当てる

サインアップすると、お住まいの国や地域により異なる、通話可能分数を取得します。 国または地域の検索が表示される時間 (分) 数を確認することができます[ここ](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。 この通話可能分数を使い切ると、通話は切断されます。 これを回避するには、コミュニケーション クレジットを設定する必要があります。
  
これを実行するには、 **電話会議または電話システムのライセンス** をユーザーに割り当てる必要があります。
  
- **電話会議**ライセンスをユーザーに自分に割り当てます。 [マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。
    
    このライセンスを割り当てた後、電話会議を設定する必要があります。 手順については、 [Office 365 に電話会議を購入するか](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)を参照してください。
    
- **電話システム**と国内または国内および海外の計画を呼び出してライセンスをユーザーに割り当てます。 [マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。
    
    > [!NOTE]
    > 通信のクレジットの必須ではありませんが、まだも**国内を呼び出すことを計画**または、**国内および国際を呼び出す予定**のライセンスを割り当てる必要があります。
  
    これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号組織内のユーザーに割り当てる必要があります。詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。
    
詳細については、[マイクロソフトのチームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>手順 2: 組織のためにコミュニケーション クレジットをセットアップする

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Office 365 の管理ページの左側のナビゲーションでは、**請求**に移動 > **購読** > **サブスクリプションを追加**します。

3. **アドオンのサブスクリプション**を展開し、**通信のクレジット**を選択し、 > **今すぐ購入**します。
    
4. **通信のクレジット**申し込みのページでの情報を入力し、[**次へ**] をクリックします。
    
   - **預金**: アカウントに投入する金額を入力します。自動再チャージを有効にしない場合、これらの利用可能残高が使い果たされると、コミュニケーション クレジットを使用して有効になっている通話機能に支障が生じます (着信無料通話サービスなど)。残高が 0 になるたびにコミュニケーション クレジットの残高を手動で補充することを回避するには、自動再チャージ機能を有効にすることを推奨します。
    
   - **自動再チャージ**: 自動再チャージを有効にすると、お使いのアカウントに対して設定したしきい値を下回ると自動的に再補充されます。
    
     コミュニケーション クレジットの残高が 0 になることで発生するサービスの支障を回避するために [ **自動再チャージ** ] 設定を使用することを推奨します。再チャージ トランザクションが成功した場合、失敗した場合 (クレジット カードの有効期限が切れているなど)、およびコミュニケーション クレジットの残高が 0 になったときに、それぞれ電子メールを受け取ります。
    
   - **リチャージ金額**: [ **リチャージの方法**] ボックスに、お使いのアカウントで下限額を下回ると追加される金額を入力します。
    
   - **下限額**: [ **残高が次の金額以下になったときに充填**] ボックスに、自動再チャージを「 *トリガー*  」する基準として使用される金額を入力します。残高がこの金額を下回ると、再チャージの金額が自動的にお使いのアカウントに追加されます。

      > [!NOTE]
     > 利用可能残高は、サービス利用時の Microsoft が公開しているレートで、コミュニケーション クレジットのみに適用されます。購入日から 12 か月以内に使用されなかった残高は、有効期限切れとなり、使用できなくなります。 
    
5. 支払い情報を入力して、[ **注文**] をクリックします。
    >[!IMPORTANT]
    >一括ライセンス契約の場合は、支払いにエンタープライズ契約番号を選択できます。 エンタープライズ契約番号が複数ある場合は、どのエンタープライズ アグリーメントを支払いに使用するかを選択することができます。 エンタープライズ 契約番号 (存在する場合) に関連付けるよう、特定の発注書番号を指定することもできます。
    
Each organization will have a different usage of Calling Plan volume and rates to consider. You will need to get this type of usage data from your current service provider. Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.
  
コミュニケーション クレジットを設定する場合は、組織の通話の利用状況を調べて、入力する必要のある料金を決める必要があります。 通話の利用状況の情報は、[ **PSTN 利用状況の詳細**] レポートで確認できます。 データを保存するためにエクスポートしたり、カスタム レポートを作成したりする場合は、このレポートを使うと、通話データ記録を Excel にエクスポートできます。 使用状況を表示するには、 [Skype ビジネス PSTN の使用状況レポート](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)を参照してください。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>手順 3: コミュニケーション クレジットのライセンスをユーザーに割り当てる

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Office 365 管理ページの左側のナビゲーションで、 **ユーザー** > **アクティブなユーザー** に進み、そのリストから一人、または複数のユーザーを選択します。
    
3. 操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。
    
4. [**製品ライセンス**] ページで、**上**、本ライセンスを割り当てるには、**通信のクレジット**を切り替えるし、[**保存**] をクリックします。
    
    > [!NOTE]
    > **Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、この手順を行うことをお勧めします。
  
## <a name="want-to-know-about-plans-and-pricing"></a>プランと価格の詳細情報

次のいずれかのリンクにアクセスすると、プランと価格を確認できます。
  
- [通話プラン](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [オーディオ会議の計画](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [電話システム プラン](https://go.microsoft.com/fwlink/?LinkId=799763)
    
You can also see information by [signing in to the Office 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.
  
ライセンスまたはライセンスの機能ごとにする必要があるテーブルを表示するには、[マイクロソフトのチームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。
  
## <a name="related-topics"></a>関連トピック

- [Skype for Business Online のセットアップ](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [電話システム ボイスメールのセットアップ - 管理者ヘルプ](set-up-phone-system-voicemail.md)
    
- [呼び出しプランの設定](set-up-calling-plans.md) および [Office 365 の呼び出しプラン](calling-plans-for-office-365.md)
    
- [資金を追加してコミュニケーション クレジットを管理する](add-funds-and-manage-communications-credits.md)
    
  
 