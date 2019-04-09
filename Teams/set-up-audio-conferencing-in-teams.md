---
title: マイクロソフト チームの電話会議を設定します
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
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '電話会議に参加するのには、電話を使用する必要があるビジネス人のダイヤルインまたはオーディオ会議を設定する方法について説明します。 '
ms.openlocfilehash: 7ff24dd2b29eabbad46759471b69c3619e4e7b24
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517177"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>マイクロソフト チームの電話会議を設定します

自分の組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 マイクロソフトのチームには、これだけの音声会議機能が含まれています! 人は、チームのアプリケーションを使用して、モバイル デバイスまたは PC 上ではなく、電話を使用してチームのミーティング呼び出すことができます。 
  
電話会議のセットアップは、ミーティングのスケジュールを設定するユーザーまたはミーティングを主催するユーザーにのみ必要です。 ダイヤルインする会議参加者には、割り当てられたライセンスやその他のセットアップは必要ありません。
  
電話会議についてよく寄せられる質問については、「[電話会議についてよくある質問](audio-conferencing-common-questions.md)」を参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>手順 1: 自分の国/地域で電話会議が使用可能かどうか確認する
<a name="__top"> </a>

「[国・地域別の電話会議と通話プランの利用可能状況](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を開き、ご自分の国または地域を選択して、電話会議についての情報に加えて、電話システム、通話プラン、有料・無料通話番号、コミュニケーション クレジットについての情報も取得してください。 
 
## <a name="step-2-get-and-assign-licenses"></a>手順 2: ライセンスを取得して割り当てる
 
1. 電話会議では、ダイヤルイン会議をセットアップするユーザーごとにライセンスが必要です。 オーディオ会議と、コストはどのくらいのために購入する必要がありますライセンスについては、[マイクロソフトのチームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。

    >[!NOTE] 
    > オーディオ会議は、アドオンと Office 365 エンタープライズ E5 のライセンスには含まれています。
        
2. オーディオ会議のライセンスを購入した後は、人、組織の会議やスケジュールを設定するのに割り当てる必要があります。 [ビジネス向けの Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)に、ユーザーが組織内で会議をスケジュールまたは潜在顧客を購入するを参照してください。
    
3. また、前の手順でライセンスを割り当てた同じユーザーに、コミュニケーション クレジット ライセンス (費用はかかりません) を割り当てることをおすすめします。 コミュニケーション クレジットのセットアップ方法については、「[組織向けにコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md)」を参照してください。
    
> [!NOTE]
> [1 分あたりの支払電話会議](audio-conferencing-pay-per-minute.md)を設定することもできます。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>手順 3: 会議ブリッジのサービス番号を取得する
<a name="__top"> </a>

電話会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。 会議ブリッジ用に、有料または無料のサービス番号のいずれかを取得することができます。 有料サービス番号と無料サービス番号を取得する方法は 3 通りあります。 
  
- **マイクロソフトのチーム管理センターを使用**します。 一部の国/地域のマイクロソフトのチーム管理センターを使用して、会議用ブリッジのサービス番号を取得できます。 [取得サービスの電話番号](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を参照してください。
    
- **ポートは、既存のサービスの番号**です。 ポートまたは現在のサービス プロバイダーまたは電話のキャリアからの既存の番号を Office 365 に転送。 この方法の詳細については、「[Office 365 に電話番号を移行](transfer-phone-numbers-to-office-365.md)」または「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。  
  
- **新しい番号の要求フォームを使用**します。 場合があります (国または地域) によってことはできません、マイクロソフトのチーム管理センターを使用して、新しいサービスの番号を取得するか、特定の電話番号または市外局番が必要です。 その場合は、フォームをダウンロードして記入してからマイクロソフトに返送する必要があります。 詳細については「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 」を参照してください。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>手順 4: 会議ブリッジにサービス番号を割り当てる
<a name="__top"> </a>

会議用ブリッジは、有料または無料の電話番号を取得するとは、会議出席依頼に使用できるように番号を割り当てる必要があります。  

オーディオ会議ブリッジは、新しい電話番号を割り当てるにはこれらの手順に従います。

![デバイスのロゴ-30x30.png](media/sfb-logo-30x30.png) **ビジネス管理センターに、Skype を使用する:**

 1. **Microsoft 365 管理センター**を参照して > **管理センター** > **チーム** > **従来のポータル**です。
 2. **音声**を選択して > **の電話番号**です。
 3. 電話番号を選択し、[**割り当て**] をクリックします。

詳細については、[変更オーディオ会議ブリッジの電話番号](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)を参照してください。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>手順 5: 会議ブリッジ用の既定言語と第 2 言語を設定する
<a name="__top"></a> [自動アテンダントの言語のマイクロソフトのチームでのオーディオ会議を設定](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)するにダイヤルするときの電話番号に電話会議の呼び出し元を呼びかけられるように設定するのには、会議自動アテンダントを使用する次に、します。 

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **マイクロソフト チームの管理センターを使用**します。

1. **会議**には、ダッシュ ボードから > **会議ブリッジ**です。
2. 会議ブリッジの電話番号を選択して**編集**を、既定の言語を選択します。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>手順 6: 会議ブリッジを設定する
<a name="__top"> </a>
    
会議ブリッジをセットアップした後、使用する開始/終了の通知と PIN の長さが正しいかなど、既定の設定を確認します。正しくない場合は、変更することができます。 

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **マイクロソフト チームの管理センターを使用**します。

1. **会議**には、ダッシュ ボードから > **会議ブリッジ**です。
2. **ブリッジの設定**を選択します。 [**ブリッジの設定**] ウィンドウが開きます。 

詳細については、[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md) を参照してください。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>手順 7: 会議を開催するユーザー向けにダイヤルインの電話番号を割り当てる

電話会議ブリッジを作成した後、ユーザー向けに有料番号と無料番号を設定する必要があります。

この操作を、会議を主催したり計画している組織内のすべてのユーザーに対して行う必要があります。 

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **マイクロソフト チームの管理センターを使用**します。

1. ダッシュ ボードで、[**ユーザー**] をクリックし、ボックスの一覧からユーザーを選択して**編集**を選択します。
2. **オーディオ会議**の横の**編集**を選択して、**オーディオ会議**ウィンドウで、**有料電話番号**や**フリー ダイヤル**番号のリスト内の数値。

さらに詳細が必要な場合は、「[Microsoft を電話会議プロバイダーとして割り当てる](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)」を参照してください。


## <a name="step-8-set-up-meeting-invitations-optional"></a>手順 8: 会議の招集をセットアップする（オプション）
<a name="__top"> </a>
 
ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議招集に自動的に追加されます。 ただし、必要に応じて、独自のヘルプや法律のリンク、テキスト メッセージ、小さな会社のグラフィックを追加できます。 [ミーティングの招待状をカスタマイズする](customize-meeting-invitations.md)を参照してください。
   
## <a name="related-topics"></a>関連トピック

[電話会議に関するよくある質問](audio-conferencing-common-questions.md)
  
[Microsoft Teams での電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md)
  
[オンライン会議、電話会議のオプションを設定](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
