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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: f19f51662a2a954b268a6c36f6c9dc0b4b90fdd8
ms.sourcegitcommit: 384e123f3b5cf1600ebd5ddd69bd022f9b8ba0f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "35861843"
---
# <a name="set-up-communications-credits-for-your-organization"></a>組織のために通信クレジットをセットアップする

Skype for Business または Microsoft Teams で無料番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。通話プラン (国内または国際) と電話会議のユーザーのうち、**すべての発信先**にダイヤルアウトできるようにする必要があるユーザーについてもコミュニケーション クレジットを設定することをお勧めします。通話プランと電話会議のサブクリプションには多くの国や地域が含まれていますが、一部の発信先は含まれていない場合があります。コミュニケーション クレジットの請求に関する設定をせずに**コミュニケーション クレジット** ライセンスをユーザーに割り当ている状態で組織の持つ分数 (使用する国/地域の通話プランまたは電話会議プランにより異なります) が使い切られた場合、これらのユーザーは電話会議から発信またはダイヤルアウトできなくなります。推奨される入金額などの詳細情報については、「[コミュニケーション クレジットについて](what-are-communications-credits.md)」を参照してください。
  
> [!NOTE]
> 必要なコストを確認するには、[こちらで料金を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>手順 1: 電話会議または通話プランのライセンスをユーザーに割り当てる

サインアップすると、お住まいの国や地域により異なる、通話可能分数を取得します。 [ここで](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)、お住まいの国または地域の検索に使用できる分数を確認できます。 この通話可能分数を使い切ると、通話は切断されます。 これを回避するには、コミュニケーション クレジットを設定する必要があります。
  
これを実行するには、 **電話会議または電話システムのライセンス** をユーザーに割り当てる必要があります。
  
- **電話会議**ライセンスをユーザーに自分に割り当てます。 「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。
    
    このライセンスを割り当てた後、電話会議を設定する必要があります。 詳細な手順については、「 [Office 365 で電話会議を試用または購入](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)する」を参照してください。
    
- **電話システム**と国内または国内および国際通話プランのライセンスをユーザーに割り当てます。 「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。
    
    > [!NOTE]
    > 通信クレジットについては必須ではありませんが、**国内通話プラン**または**国内および国際通話プラン**のライセンスを割り当てる必要があります。
  
    これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号組織内のユーザーに割り当てる必要があります。詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。
    
詳細については、「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>手順 2: 組織のためにコミュニケーション クレジットをセットアップする

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Microsoft 365 管理センターの左のナビゲーションで、[**サブスクリプション** > の**** > **追加**] に移動します。

3. **アドオンサブスクリプション**を展開し、[**通信クレジット** > の**今すぐ購入**] を選択します。
    
4. [**通信クレジット**のサブスクリプション] ページで、情報を入力し、[**次へ**] をクリックします。
    
   - **預金**: アカウントに投入する金額を入力します。自動再チャージを有効にしない場合、これらの利用可能残高が使い果たされると、コミュニケーション クレジットを使用して有効になっている通話機能に支障が生じます (着信無料通話サービスなど)。残高が 0 になるたびにコミュニケーション クレジットの残高を手動で補充することを回避するには、自動再チャージ機能を有効にすることを推奨します。
    
   - **自動再チャージ**: 自動再チャージを有効にすると、お使いのアカウントに対して設定したしきい値を下回ると自動的に再補充されます。
    
     コミュニケーション クレジットの残高が 0 になることで発生するサービスの支障を回避するために [ **自動再チャージ** ] 設定を使用することを推奨します。再チャージ トランザクションが成功した場合、失敗した場合 (クレジット カードの有効期限が切れているなど)、およびコミュニケーション クレジットの残高が 0 になったときに、それぞれ電子メールを受け取ります。
    
   - **リチャージ金額**: [ **リチャージの方法**] ボックスに、お使いのアカウントで下限額を下回ると追加される金額を入力します。
    
   - **下限額**: [ **残高が次の金額以下になったときに充填**] ボックスに、自動再チャージを「 *トリガー*  」する基準として使用される金額を入力します。残高がこの金額を下回ると、再チャージの金額が自動的にお使いのアカウントに追加されます。

      > [!NOTE]
     > 利用可能残高は、サービス利用時の Microsoft が公開しているレートで、コミュニケーション クレジットのみに適用されます。購入日から 12 か月以内に使用されなかった残高は、有効期限切れとなり、使用できなくなります。 
     > 
     > 毎月の通信クレジットの請求は、alloted 基金が使用されている場合にのみ適用されます。毎月の使用状況を確認する方法については、「 [Skype For BUSINESS PSTN 使用状況レポート](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)」を参照してください。
    
5. 支払い情報を入力して、[**注文**] をクリックします。
    >[!IMPORTANT]
    >ボリューム ライセンスをお持ちのお客様は、支払い方法としてエンタープライズ契約番号を選択できます。エンタープライズ契約番号が複数ある場合は、支払いに使用するエンタープライズ契約番号を選択できます。(該当する場合は) エンタープライズ契約番号に関連付ける発注書番号を指定することもできます。
    
Each organization will have a different usage of Calling Plan volume and rates to consider. You will need to get this type of usage data from your current service provider. Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.
  
通信クレジットを設定している場合は、組織の通話使用状況を調査して、必要な金額を確認する必要があります。 通話の利用状況の情報は、[ **PSTN 利用状況の詳細**] レポートで確認できます。 このレポートでは、データを保存したり、カスタムレポートを作成したりする必要がある場合に、通話データレコードを Excel にエクスポートすることができます。 使用状況の確認方法については、「 [Skype For BUSINESS PSTN 使用状況レポート](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)」を参照してください。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>手順 3: コミュニケーション クレジットのライセンスをユーザーに割り当てる

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Microsoft 365 管理センターの左側のナビゲーションで、[**ユーザー**]  >  [**アクティブなユーザー**] に進み、そのリストから一人、または複数のユーザーを選択します。
    
3. [操作] ウィンドウの [**製品ライセンス**] で [**編集**] をクリックします。
    
4. このライセンスを割り当てるには、[**製品ライセンス**] ページで [**コミュニケーション クレジット**] を [**オン**] に切り替え、[**保存**] をクリックします。
    
    > [!NOTE]
    > **Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、これを実行することをお勧めします。
  
## <a name="want-to-know-about-plans-and-pricing"></a>プランと価格の詳細情報

次のいずれかのリンクにアクセスすると、プランと価格を確認できます。
  
- [通話プラン](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [電話会議プラン](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [電話システム プラン](https://go.microsoft.com/fwlink/?LinkId=799763)
    
[Microsoft 365 管理センターにサインイン](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)して、[サブスクリプションの**** > **** > **追加**] サブスクリプションに移動して、情報を表示することもできます。
  
各機能に必要なライセンスの表を表示するには、「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。
  
## <a name="related-topics"></a>関連トピック

- [Skype for Business Online のセットアップ](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [クラウド ボイスメールのセットアップ - Admin ヘルプ](set-up-phone-system-voicemail.md)
    
- [呼び出しプランの設定](set-up-calling-plans.md) および [Office 365 の呼び出しプラン](calling-plans-for-office-365.md)
    
- [資金を追加してコミュニケーション クレジットを管理する](add-funds-and-manage-communications-credits.md)
    
  
 
