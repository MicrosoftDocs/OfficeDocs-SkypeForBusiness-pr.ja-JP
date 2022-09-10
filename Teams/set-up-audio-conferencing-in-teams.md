---
title: Microsoft Teams の電話会議を設定する
ms.author: heidip
author: MicrosoftHeidi
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
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '電話を使用して電話会議に参加する必要がある社内ユーザーのダイヤルイン会議または電話会議をセットアップする方法について説明します。 '
ms.openlocfilehash: 04c29b6eaf13d12bee1395d913519c971c7a25d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642128"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Microsoft Teams の電話会議を設定する

組織のメンバーが電話で会議に参加することが必要になる場合があります。Microsoft Teams では、このようなシチュエーションで活用できる電話会議機能が提供されています。ユーザーは、モバイル デバイスや PC 上の Microsoft Teams アプリを使用することなく、電話を使用して Microsoft Teams の会議に参加できます。
  
電話会議の設定は、会議のスケジュールを設定または会議を進行するユーザーに対してのみ必要です。ダイヤルインで参加するユーザーについては、ライセンスの割り当てや他の設定は必要ありません。
  
電話会議についてよく寄せられる質問については、 [電話会議についてよくある質問](audio-conferencing-common-questions.md) を参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>手順 1: 自分の国/地域で電話会議が使用可能かどうか確認する

「[国・地域別の電話会議と通話プランの利用可能状況](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を開き、ご自分の国または地域を選択して、電話会議についての情報に加えて、電話システム、通話プラン、有料・無料通話番号、コミュニケーション クレジットについての情報も取得してください。

## <a name="step-2-get-and-assign-licenses"></a>手順 2: ライセンスを取得して割り当てる

1. 電話会議では、ダイヤルイン会議をセットアップするユーザーごとにライセンスが必要です。 電話会議のために購入する必要のあるライセンスの種類と必要コストについては、「[Microsoft Teams のアドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

    >[!NOTE]
    > 電話会議は Office 365 Enterprise E5 ライセンスにアドオンとして含まれています。

2. 電話会議ライセンスを購入した後は、それらのライセンスを、会議を計画または開催しようとしている組織内のユーザーに割り当てる必要があります。 「[Microsoft 365 または一般法人向け Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」を参照して、会議をスケジュールまたは主催することになる組織内のユーザーのために購入したライセンス割り当てます。

3. また、前の手順でライセンスを割り当てた同じユーザーに、コミュニケーション クレジット ライセンス (費用はかかりません) を割り当てることをおすすめします。 コミュニケーション クレジットのセットアップ方法については、「[組織向けにコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md)」を参照してください。

   > [!NOTE]
   > [分毎課金の電話会議](audio-conferencing-pay-per-minute.md)をセットアップすることもできます。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>手順 3: 会議ブリッジのサービス番号を取得する

電話会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。 会議ブリッジ用に、有料または無料のサービス番号のいずれかを取得することができます。 有料サービス番号と無料サービス番号を取得する方法は 3 通りあります。
  
- **Microsoft Teams 管理センターを使用** する。 いくつかの国/地域では、Microsoft Teams 管理センターを使用して、会議ブリッジ用にサービス番号を取得できます。 「[サービス電話番号の取得](./getting-service-phone-numbers.md)」を参照してください。

- **既存のサービス番号を移行する**。 既存の番号を現在のサービス プロバイダーまたは電話会社から Microsoft 365 または Office 365 に移行または転送します。 この方法の詳細については、「[Teams に電話番号を移行する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」または「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。  
  
- **申請書を使用して新しい番号を求める**。 国または地域によっては Microsoft Teams 管理センターを使用して新しい電話番号を取得することができない場合があります。あるいは、特定の電話番号またはエリアコードが必要です。 その場合は、申請書をダウンロードして送信する必要があります。 詳細については「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 」を参照してください。

## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>手順 4: 会議ブリッジにサービス番号を割り当てる

会議ブリッジ用に有料電話番号と無料電話番号のいずれかまたは両方を取得したら、それらの番号を割り当てて、会議の招集に使用できるようにする必要があります。  

電話会議ブリッジに新規の電話番号を割り当てるには、以下の手順を実行します。

 **Microsoft Teams 管理センターの使用**:

 1. [ホーム] から **[音声]** > **[電話番号]** に移動します。
 2. 電話番号を選択し、**[割り当て]** をクリックします。

詳細については、「[電話会議ブリッジの電話番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)」を参照してください。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>手順 5: 会議ブリッジの既定の言語と代替言語を設定する

 次に、電話会議の電話番号にダイヤルインした時に、呼び出しをしたユーザーに挨拶するために会議の自動応答で使用する、[Microsoft Teams の電話会議の自動応答の言語を設定](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)します。

 **Microsoft Teams 管理センターの使用**:

1. [ホーム] から **[会議]** > **[会議ブリッジ]** に移動します。
2. 会議ブリッジ電話番号を選択して **[編集]** をクリックし、既定の言語を選択します。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>手順 6: 会議ブリッジを設定する

会議ブリッジをセットアップした後、使用する開始/終了の通知と PIN の長さが正しいかなど、既定の設定を確認します。正しくない場合は、変更することができます。

 **Microsoft Teams 管理センターの使用**:

1. [ホーム] から **[会議]** > **[会議ブリッジ]** に移動します。
2. **[ブリッジの設定]** を選択すると、**[ブリッジの設定]** ペインが開きます。

詳細については、[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md) を参照してください。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>手順 7: 会議を開催するユーザー向けにダイヤルインの電話番号を割り当てる

[「Microsoft Teams の招待に含まれる電話番号を設定する」を参照してください](set-the-phone-numbers-included-on-invites-in-teams.md)。

> [!NOTE]
> *TeamsAudioconferencingpolicy* に電話番号を追加し、ポリシーをユーザーに割り当てることで電話番号を設定することもできます。 ポリシーに追加された有料電話番号とフリーダイヤル電話番号は、電話会議設定ウィンドウでユーザーに対して個別に設定された電話番号よりも優先されます。 *Teamsaudioconferencingpolicy* に電話番号が追加されていない場合は、電話会議の設定ウィンドウでユーザーに個別に設定された電話番号が Microsoft Teams の会議出席依頼に表示されます。 [有料電話番号とフリーダイヤル番号の電話会議ポリシー設定](audio-conferencing-toll-free-numbers-policy.md) の詳細については、以下をご覧ください。

> [!IMPORTANT]
> 割り当てられた電話番号が会議出席依頼に表示されるまでには、最大で 24 時間かかる場合があります。 更新された番号が表示されない場合は、少なくとも 24 時間待ってからサポートにお問い合わせください。

## <a name="step-8-set-up-meeting-invitations-optional"></a>手順 8: 会議の招集をセットアップする（オプション）

出席者に送信される会議の出席依頼には、ユーザーに設定されているダイヤルイン番号が自動的に追加されますが、望むなら、独自のヘルプ、法的事項へのリンク、テキスト メッセージ、および小さな会社ロゴを追加できます。「[会議出席依頼のカスタマイズ](meeting-settings-in-teams.md#customize-meeting-invitations)」を参照してください。

## <a name="related-topics"></a>関連項目

[電話会議に関するよくある質問](audio-conferencing-common-questions.md)
  
[Microsoft Teams での電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md)
  
[オンライン会議、電話会議のオプションを設定](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
