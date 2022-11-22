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
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization.
ms.openlocfilehash: 0a6489b0c3e7591139421b418be52d6bfcd8f4fa
ms.sourcegitcommit: 0a13f96663c7466b08d654bedcb6206f302189a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2022
ms.locfileid: "69139131"
---
# <a name="set-up-communications-credits-for-your-organization"></a>組織のために通信クレジットをセットアップする

Microsoft Teams でフリーダイヤル番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。 Microsoft では、Microsoft Teams 通話プラン (国内、国際、または従量課金制) と、 **任意の宛先** にダイヤルアウトする必要がある電話会議ユーザーのコミュニケーション クレジットを設定することをお勧めします。 通話プランまたは電話会議サブスクリプションには、一部の宛先が含まれていない場合があります。

通話プランや電話会議にサインアップすると、国/地域に応じて数分かかります。 詳細については、「 [電話会議と通話プランの国または地域の可用性リスト](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization)」を参照してください。

コミュニケーション クレジットを設定していない場合、組織で数分を使い果たすと、それらのユーザーは電話会議会議から通話やダイヤルアウトを行うことができなくなります。 「[コミュニケーション クレジットとは](what-are-communications-credits.md)」を参照すると、推奨される資金調達金額など、より多くの情報を得ることができます。
  
プランと価格の詳細については、 [こちらの料金を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=799523)。

> [!IMPORTANT]
> **新しいコマース エクスペリエンスでサブスクリプションを呼び出しているお客様の場合:**
>
> 新しいコマース エクスペリエンス (NCE) を使用すると、サービスが使用された後のサービスの支払い (使用後の課金とも呼ばれます) を顧客が支払うことができます。
>
> コミュニケーション クレジットは、発信分をサポートするための前払い予算であるため、NCE 通話サブスクリプションをお持ちのお客様は購入できません。
>
> 代わりに、NCE のお客様は、使用後数分後に超過分の支払いを行います。 コミュニケーション クレジットのプールは必要ありません。
>
> サブスクリプションを呼び出すための新しいコマース エクスペリエンスの詳細については、「サブスクリプションの [従量課金制を有効にする](/microsoft-365/commerce/subscriptions/manage-pay-as-you-go-services) 」と「 [電話会社の従量課金制の新しいコマース超過](/partner-center/new-commerce-telco-payg)分」を参照してください。

組織のコミュニケーション クレジットを設定するには、次の手順に従います。

1. [通話プランライセンスを持つ電話会議または電話システムをユーザーに割り当てます](#step-1-assign-an-audio-conferencing-andor-phone-system-with-calling-plan-license-to-your-users)。

2. [組織のコミュニケーション クレジットを設定](#step-2-set-up-communications-credits-for-your-organization)します。

3. [コミュニケーション クレジット ライセンスをユーザーに割り当てます](#step-3-assign-a-communications-credits-license-to-users)。
  
## <a name="step-1-assign-an-audio-conferencing-andor-phone-system-with-calling-plan-license-to-your-users"></a>手順 1: 通話プランライセンスを持つ電話会議または電話システムをユーザーに割り当てる
  
コミュニケーション クレジットは、電話会議ライセンス、通話プラン ライセンスを持つ電話システム、またはその両方を持つユーザーに対して有効にすることができます。
  
- **電話会議** ライセンスをユーザーに自分に割り当てます。 [「Microsoft Teams アドオン ライセンスを割り当てる」を](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)参照してください。

  このライセンスを割り当てた後、電話会議を設定する必要があります。 詳細な手順については、「[Microsoft 365 または Office 365で電話会議を試すか購入する](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)」を参照してください。

- **電話システム** と **、国内**、**国際**、または **従量課金** 制通話プランのライセンスをユーザーに割り当てます。 [「Microsoft Teams アドオン ライセンスを割り当てる」を](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)参照してください。

  > [!NOTE]
  > 通信クレジットには必要ありませんが、 **国内通話プラン**、 **国際通話プラン**、従 **量課金** 制ライセンスを割り当てる必要があります。
  
  これらのライセンスを割り当てた後、組織の電話番号を取得し、その番号を組織内のユーザーに割り当てる必要があります。 詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。

詳細については、「 [Microsoft Teams アドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>手順 2: 組織のためにコミュニケーション クレジットをセットアップする

1. 職場または学校アカウントで[Microsoft 365 管理センター](https://portal.office.com/Adminportal)にサインインします。

2. Microsoft 365 管理センターの左側のナビゲーションで、[課金 **購入サービス****]** >  に移動します。

3. **[アドオン**] カテゴリの [**コミュニケーション クレジット**] を探すか、[**すべての製品** カテゴリの検索] 検索ボックスで **コミュニケーション クレジット** を検索し、[詳細] を選択 **します**。

4. サービス情報を確認し、[ **購入**] を選択します。 (注: コミュニケーション クレジット ライセンスの固定数は、すべての順序で自動的に選択されます)。

5. [チェックアウト] ページで、支払い情報を入力し、必要な情報を入力します。

   - **預金**: アカウントに投入する金額を入力します。

   - **自動再チャージ**: 自動再チャージを有効にすると、お使いのアカウントに対して設定したしきい値を下回ると自動的に再補充されます。

     Microsoft では、通信クレジットの残高がゼロに達した場合にサービスの中断を回避するために **、自動再充電** 設定を使用することをお勧めします。 再充電トランザクションが成功したとき、再充電トランザクションが失敗した場合 (クレジット カードの有効期限が切れた場合など)、コミュニケーション クレジットの残高が 0 に達すると、メールが送信されます。

   - **リチャージ金額**: [ **リチャージの方法**] ボックスに、お使いのアカウントで下限額を下回ると追加される金額を入力します。

   - **Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge. Once your balance falls below this amount, the recharge amount will be added automatically to your account.

      > [!NOTE]
     > Funds will be applied only to Communications Credits at Microsoft published rates when the services are used. Any funds not used within 12 months of the purchase date will expire and be forfeited.
     >
     > 自動再充電機能を使用する場合、トリガー金額に達し、再充電トランザクションが処理されると、通信クレジットの請求が生成されます。 通信クレジットの金額は、最初のアウトの方法で最初に使用されます。 毎月の使用状況を確認する方法については、「 [Microsoft Teams PSTN 使用状況レポート](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)」を参照してください。

6. **[注文]** を選択します。

    >[!IMPORTANT]
    >ボリューム ライセンスのお客様の場合は、エンタープライズ契約を使用して支払いを行うことができます。 エンタープライズ契約番号が複数ある場合は、どのエンタープライズ アグリーメントを支払いに使用するかを選択することができます。 また、サポートがこれを有効にすると、エンタープライズ契約番号 (該当する場合) に関連付ける発注書番号を指定する機会も提供されます。

Each organization will have a different usage of Calling Plan volume and rates to consider. 現在のサービス プロバイダーからこの種類の使用状況データを取得する必要があります。 Microsoft Teams をサービス プロバイダーとして既に使用している組織は、**Microsoft Teams 管理センター** > **の分析&レポート** の **使用状況レポート** >  > **PSTN と SMS (プレビュー) 使用状況** レポートで確認することで、使用状況データを取得できます。
  
コミュニケーション クレジットを設定するときは、組織の通話の使用状況を調査して、必要な量を特定する必要があります。 通話使用状況情報を取得するには、 **PSTN と SMS (プレビュー) 使用状況** レポートを確認します。 このレポートを使用すると、データを格納したり、カスタム レポートを作成したりする必要がある場合に、呼び出しデータ レコードを Excel にエクスポートできます。 使用状況を確認する方法については、「 [Microsoft Teams PSTN 使用状況レポート」を参照](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)してください。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>手順 3: コミュニケーション クレジットのライセンスをユーザーに割り当てる

1. 職場または学校アカウントで[Microsoft 365 管理センター](https://portal.office.com/Adminportal)にサインインします。

2. Microsoft 365 管理センターの左側のナビゲーションで、[アクティブ **なユーザー****]** >  に移動し、一覧からユーザーを選択します。

3. [ **ライセンスとアプリ]** を選択します。

4. **[コミュニケーション クレジット**] を **[オン]** に切り替えてこのライセンスを割り当て、[保存] を選択 **します**。

    > [!NOTE]
    > **Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、これを実行することをお勧めします。

    > [!TIP]
    > [Powershell](/powershell/module/skype/?view=skype-ps&preserve-view=true) を使用して、1 つのコマンドを使用して複数のユーザーにライセンスとアプリを割り当てることができます。
  
## <a name="for-more-information"></a>関連情報

- 詳細については、[Microsoft 365 管理センターにサインインし](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)、[**課金** > **サブスクリプション][ サブスクリプションの** > **追加]** に移動します。
  
- ライセンスの詳細については、「 [Microsoft Teams アドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

- 通話プランの詳細については、「通話 [プランの設定](set-up-calling-plans.md) 」および「 [Microsoft 365 の通話プラン](calling-plans-for-office-365.md)」を参照してください。

- 資金の追加とコミュニケーション クレジットの管理の詳細については、「 [資金の追加とコミュニケーション クレジットの管理](add-funds-and-manage-communications-credits.md)」を参照してください。
