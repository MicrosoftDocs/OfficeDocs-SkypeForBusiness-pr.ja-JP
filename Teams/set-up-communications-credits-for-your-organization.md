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
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 98591d7603cdf63a76bef3478834f37504d8ff6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117105"
---
# <a name="set-up-communications-credits-for-your-organization"></a>組織のために通信クレジットをセットアップする

Skype for Business または Microsoft Teams で無料番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。通話プラン (国内または国際) と電話会議のユーザーのうち、**すべての発信先** にダイヤルアウトできるようにする必要があるユーザーについてもコミュニケーション クレジットを設定することをお勧めします。通話プランと電話会議のサブクリプションには多くの国や地域が含まれていますが、一部の発信先は含まれていない場合があります。コミュニケーション クレジットの請求に関する設定をせずに **コミュニケーション クレジット** ライセンスをユーザーに割り当ている状態で組織の持つ分数 (使用する国/地域の通話プランまたは電話会議プランにより異なります) が使い切られた場合、これらのユーザーは電話会議から発信またはダイヤルアウトできなくなります。推奨される入金額などの詳細情報については、「[コミュニケーション クレジットについて](what-are-communications-credits.md)」を参照してください。
  
> [!NOTE]
> 必要なコストを確認するには、[こちらで料金を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>手順 1: 電話会議または通話プランのライセンスをユーザーに割り当てる

サインアップすると、お住まいの国や地域により異なる、通話可能分数を取得します。 [電話会議] と [通話プラン] の [国または [地域](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) ] の一覧で国または地域を検索して、取得する分数を確認できます。 この通話可能分数を使い切ると、通話は切断されます。 これを回避するには、コミュニケーション クレジットを設定する必要があります。
  
これを実行するには、 **電話会議または電話システムのライセンス** をユーザーに割り当てる必要があります。
  
- **電話会議** ライセンスをユーザーに自分に割り当てます。 「[アドオン ライセンスMicrosoft Teams割り当てる」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
    このライセンスを割り当てた後、電話会議を設定する必要があります。 詳しい手順については、「電話会議を試用または購入する」を参照Microsoft 365[または Office 365。](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
- ユーザー **電話システム** 国内通話プランまたは国内 **通話** プランと国際通話プランのライセンスを割り当てる。 「[アドオン ライセンスMicrosoft Teams割り当てる」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
    > [!NOTE]
    > 通信クレジットには必要ありませんが、国内通話プランまたは国内および国際通話プランのライセンスも割り当てる **必要** があります。
  
    これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号組織内のユーザーに割り当てる必要があります。詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。
    
詳細については、「Microsoft Teams[ライセンス」を参照してください。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>手順 2: 組織のためにコミュニケーション クレジットをセットアップする

1. 管理者センターに[Microsoft 365または](https://portal.office.com/Adminportal)学校アカウントでサインインします。
    
2. 管理センターの左側のナビゲーションMicrosoft 365、Billing Purchase Services に  >  **移動します**。 下にスクロールし、[ **アドオン] を選択します**。

3. [通信 **クレジット] を選択します**。
    
4. [ **通信クレジット] サブスクリプション** ページで、情報を入力し、[次へ] を **クリックします**。
    
   - **預金**: アカウントに投入する金額を入力します。自動再チャージを有効にしない場合、これらの利用可能残高が使い果たされると、コミュニケーション クレジットを使用して有効になっている通話機能に支障が生じます (着信無料通話サービスなど)。残高が 0 になるたびにコミュニケーション クレジットの残高を手動で補充することを回避するには、自動再チャージ機能を有効にすることを推奨します。
    
   - **自動再チャージ**: 自動再チャージを有効にすると、お使いのアカウントに対して設定したしきい値を下回ると自動的に再補充されます。
    
     コミュニケーション クレジットの残高が 0 になることで発生するサービスの支障を回避するために [ **自動再チャージ** ] 設定を使用することを推奨します。再チャージ トランザクションが成功した場合、失敗した場合 (クレジット カードの有効期限が切れているなど)、およびコミュニケーション クレジットの残高が 0 になったときに、それぞれ電子メールを受け取ります。
    
   - **リチャージ金額**: [ **リチャージの方法**] ボックスに、お使いのアカウントで下限額を下回ると追加される金額を入力します。
    
   - **下限額**: [ **残高が次の金額以下になったときに充填**] ボックスに、自動再チャージを「 *トリガー*  」する基準として使用される金額を入力します。残高がこの金額を下回ると、再チャージの金額が自動的にお使いのアカウントに追加されます。

      > [!NOTE]
     > 利用可能残高は、サービス利用時の Microsoft が公開しているレートで、コミュニケーション クレジットのみに適用されます。購入日から 12 か月以内に使用されなかった残高は、有効期限切れとなり、使用できなくなります。 
     > 
     > 通信クレジットの毎月の課金は、関連付けられている資金が使用されている場合にのみ適用されます。毎月の使用状況を確認する方法については、「PSTN 使用状況レポートSkype for Business[参照してください](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)。
    
5. 支払い情報を入力して、[**注文**] をクリックします。
    >[!IMPORTANT]
    >ボリューム ライセンスをお持ちのお客様は、支払い方法としてエンタープライズ契約番号を選択できます。エンタープライズ契約番号が複数ある場合は、支払いに使用するエンタープライズ契約番号を選択できます。(該当する場合は) エンタープライズ契約番号に関連付ける発注書番号を指定することもできます。
    
Each organization will have a different usage of Calling Plan volume and rates to consider. You will need to get this type of usage data from your current service provider. サービス プロバイダーとして Skype for Business Online を既に使用している組織は、Microsoft Teams **管理** センターの [PSTN 使用状況の詳細レポート] レポートで確認することで使用状況データを  >    >  **取得** できます。
  
通信クレジットを設定する場合は、組織の通話の使用状況を調査して、必要な金額を決定する必要があります。 通話の利用状況の情報は、[ **PSTN 利用状況の詳細**] レポートで確認できます。 このレポートを使用すると、データを保存したり、カスタム レポートExcelを作成したりする必要がある場合に、通話データ レコードをエクスポートできます。 使用状況を確認する方法については、「PSTN 使用状況レポート [」を参照してください](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>手順 3: コミュニケーション クレジットのライセンスをユーザーに割り当てる

1. 管理者センターに[Microsoft 365または](https://portal.office.com/Adminportal)学校アカウントでサインインします。
    
2. 管理センターの左側のナビゲーションMicrosoft 365[アクティブなユーザー] に移動し、  >  一覧からユーザーを選択します。
    
3. [ライセンス **とアプリ] を選択します**。
    
4. [ **通信クレジット] を** **[オン] に** 切り替え、このライセンスを割り当て、[保存] を **選択します**。
    
    > [!NOTE]
    > **Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、これを実行することをお勧めします。

    > [!TIP]
    > PowerShell を使用 [して、1](/powershell/module/skype/?view=skype-ps) つのコマンドで複数のユーザーにライセンスとアプリを割り当てできます。
  
## <a name="want-to-know-about-plans-and-pricing"></a>プランと価格の詳細情報

次のいずれかのリンクにアクセスすると、プランと価格を確認できます。
  
- [通話プラン](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [電話会議プラン](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [電話システム プラン](https://go.microsoft.com/fwlink/?LinkId=799763)
    
また、管理センターにサインイン [し、[課金サブスクリプション] [サブスクリプションの追加] Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)に移動して、情報  >    >  **を確認できます**。
  
各機能に必要なライセンスまたはライセンスを含むテーブルを表示するには[、「Microsoft Teams」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
## <a name="related-topics"></a>関連トピック

- [Skype for Business Online をセットアップする](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [クラウド ボイスメールの設定 - Admin ヘルプ](set-up-phone-system-voicemail.md)
    
- [通話プランと通話](set-up-calling-plans.md)プラン[を設定して、Microsoft 365またはOffice 365](calling-plans-for-office-365.md)
    
- [資金を追加してコミュニケーション クレジットを管理する](add-funds-and-manage-communications-credits.md)
    
  
