---
title: Microsoft Teams の電話会議をセットアップする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '電話会議への参加に電話を使用する必要がある、社内のユーザーに対してダイヤルインまたは電話会議をセットアップする方法について説明します。 '
ms.openlocfilehash: d630f6f149f61609209cc4ead23ed7232647cb08
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "37925368"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Microsoft Teams の電話会議をセットアップする

自分の組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 Microsoft Teams には、このような状況での電話会議機能が含まれています。 ユーザーは、モバイルデバイスや PC で Teams アプリを使う代わりに、電話を使って Teams 会議にコールインすることができます。 
  
電話会議の設定は、会議のスケジュールを設定または会議を進行するユーザーに対してのみ必要です。ダイヤルインで参加するユーザーについては、ライセンスの割り当てや他の設定は必要ありません。
  
電話会議についてよく寄せられる質問については、「[電話会議についてよくある質問](audio-conferencing-common-questions.md)」を参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>手順 1: 自分の国/地域で電話会議が使用可能かどうか確認する
<a name="__top"> </a>

「[国・地域別の電話会議と通話プランの利用可能状況](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を開き、ご自分の国または地域を選択して、電話会議についての情報に加えて、電話システム、通話プラン、有料・無料通話番号、コミュニケーション クレジットについての情報も取得してください。 
 
## <a name="step-2-get-and-assign-licenses"></a>手順 2: ライセンスを取得して割り当てる
 
1. 電話会議では、ダイヤルイン会議をセットアップするユーザーごとにライセンスが必要です。 電話会議用に購入する必要があるライセンスとその料金については、「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

    >[!NOTE] 
    > 電話会議は、Office 365 Enterprise E5 ライセンスとアドオンとして含まれています。
        
2. 電話会議ライセンスを購入したら、会議をスケジュールまたは開催しようとしている組織内のユーザーにそれらを割り当てる必要があります。 会議をスケジュールまたは開催しようとしている組織内のユーザーに購入した一般[法人向け Office 365 のライセンスをユーザーに割り当てる](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)方法について説明します。
    
3. また、前の手順でライセンスを割り当てた同じユーザーに、コミュニケーション クレジット ライセンス (費用はかかりません) を割り当てることをおすすめします。 コミュニケーション クレジットのセットアップ方法については、「[組織向けにコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md)」を参照してください。
    
> [!NOTE]
> 1[分あたりの通話料金](audio-conferencing-pay-per-minute.md)を設定することもできます。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>手順 3: 会議ブリッジのサービス番号を取得する
<a name="__top"> </a>

電話会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。 会議ブリッジ用に、有料または無料のサービス番号のいずれかを取得することができます。 有料サービス番号と無料サービス番号を取得する方法は 3 通りあります。 
  
- **Microsoft Teams 管理センターを使用**します。 一部の国/地域では、Microsoft Teams 管理センターを使って、会議ブリッジのサービス番号を取得できます。 「[サービスの電話番号を取得](/microsoftteams/getting-service-phone-numbers)する」をご覧ください。
    
- **既存のサービス番号を移植**します。 現在のサービスプロバイダーまたは電話会社から Office 365 に既存の電話番号を移行または転送するには、 詳細については、「[電話番号をチームに転送](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)する」または「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」を参照してください。  
  
- **新しい番号には要求フォームを使用**します。 場合によっては (お住まいの国/地域によっては)、Microsoft Teams 管理センターを使用して新しいサービス番号を取得することはできません。または、特定の電話番号または市外局番が必要です。 その場合は、申請書をダウンロードして送信する必要があります。 詳細については「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 」を参照してください。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>手順 4: 会議ブリッジにサービス番号を割り当てる
<a name="__top"> </a>

電話会議ブリッジの有料または無料の電話番号を取得したら、電話番号を割り当てて会議出席依頼に使用できるようにする必要があります。  

新しい電話番号を電話会議ブリッジに割り当てるには、次の手順に従います。

![Skype for](media/sfb-logo-30x30.png) **business 管理センターを使用し**た skype for business ロゴを示すアイコン:

 1. **Microsoft 365 管理センター** > **管理** > センター**チーム** > の従来の**ポータル**に移動します。
 2.  > [ ******電話番号**] を選択します。
 3. 電話番号を選択して、「**割り当て**」をクリックします。

詳細については、「[電話会議ブリッジの電話番号を変更](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)する」を参照してください。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>手順 5: 会議ブリッジ用の既定言語と第 2 言語を設定する
<a name="__top"></a>次に、 [Microsoft Teams の電話会議の自動応答の言語を設定](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)します。このとき、会議の自動応答で電話会議の電話番号にダイヤルインするときに、挨拶メッセージの発信者が通話を発信します。 

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン:

1. ダッシュボードで、[**会議** > **会議ブリッジ**] に移動します。
2. 会議ブリッジの電話番号を選択し、[**編集**] をクリックして、既定の言語を選択します。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>手順 6: 会議ブリッジを設定する
<a name="__top"> </a>
    
会議ブリッジをセットアップした後、使用する開始/終了の通知と PIN の長さが正しいかなど、既定の設定を確認します。正しくない場合は、変更することができます。 

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン:

1. ダッシュボードで、[**会議** > **会議ブリッジ**] に移動します。
2. [**ブリッジの設定**] を選びます。 [**ブリッジの設定**] ウィンドウが開きます。 

詳細については、[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md) を参照してください。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>手順 7: 会議を開催するユーザー向けにダイヤルインの電話番号を割り当てる

電話会議ブリッジを作成した後、ユーザー向けに有料番号と無料番号を設定する必要があります。

この操作を、会議を主催したり計画している組織内のすべてのユーザーに対して行う必要があります。 

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン:

1. ダッシュボードで、[**ユーザー**] をクリックし、一覧からユーザーを選んで、[**編集**] を選びます。
2. [電話**会議**] の横にある [**編集**] を選択し、[電話**会議**] ウィンドウで、[**有料**電話番号] と [**無料電話**番号] の一覧から番号を選びます。

さらに詳細が必要な場合は、「[Microsoft を電話会議プロバイダーとして割り当てる](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)」を参照してください。


## <a name="step-8-set-up-meeting-invitations-optional"></a>手順 8: 会議の招集をセットアップする（オプション）
<a name="__top"> </a>
 
ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議招集に自動的に追加されます。 ただし、必要に応じて、独自のヘルプや法律のリンク、テキスト メッセージ、小さな会社のグラフィックを追加できます。 「[会議出席依頼をカスタマイズ](meeting-settings-in-teams.md#customize-meeting-invitations)する」を参照してください。
   
## <a name="related-topics"></a>関連トピック

[電話会議に関するよくある質問](audio-conferencing-common-questions.md)
  
[Microsoft Teams での電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md)
  
[オンライン会議、電話会議のオプションを設定](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
