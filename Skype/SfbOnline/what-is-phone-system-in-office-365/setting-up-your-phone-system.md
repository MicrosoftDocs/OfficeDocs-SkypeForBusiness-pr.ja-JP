---
title: 組織の電話システムを設定する.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 02/28/2018
ms.topic: article
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
- Phone System
- Strat_SB_PSTN
description: '組織の電話システム (PBX をクラウド) を設定する方法について説明します。 '
ms.openlocfilehash: a9715797284f08c3d7f2ecbf3ba45a9269a5e0e0
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="setting-up-phone-system-in-your-organization"></a>組織の電話システムを設定する.

以下は、Office 365 の電話システムを設定するため、ステップ バイ ステップ ガイドのことです。 各手順の最後に、追加の詳細な情報へのリンクを利用できます。  

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>ステップ 1: 電話システムは、国または地域で利用可能なことを確認します。

1.  最初には、[オーディオ会議や予定を呼び出すための国および地域の可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)、し、ページの上部にある一覧から国または地域を選択します。 
2.  **電話システム**での機能と詳細の一覧を確認します。 
3.  電話システムが使用可能な場合は、手順 2 に進みます。 

**電話システムおよびオーディオ会議の地域に利用可能時間に関する詳細については、[オーディオ会議や予定を呼び出すための国および地域の可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)を参照してください。**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>手順 2: 購入し、電話システムおよび計画を呼び出してライセンスを割り当てる

呼び出すことを計画し、電話システムのライセンスを 1 人のユーザーに割り当てるには、手順は、Office 365 のライセンスを割り当てると同じです。 「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。 一括で複数のユーザーを割り当てる場合を参照してください (../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

## <a name="step-3-get-phone-numbers-for-your-users"></a>手順 3: ユーザーの電話番号を取得します。

[] 組織内でユーザーが電話を発着信できるように設定するには、組織のための電話番号を取得する必要があります。 

ユーザーに番号を取得する 3 つの方法があります。 
- ビジネス管理センターは、Skype を使用して、新しい番号を取得します。
- ビジネス管理センターの Skype では使用できない新しい番号を取得します。
- 現在のサービス プロバイダーまたは携帯電話会社から Office 365 に既存の番号を移行する。

[ **新しいユーザー番号を追加**] ページを使用して、電話番号の確認、検索、取得、予約を行う必要があります。 国/地域、都道府県、および市区町村を検索し、ユーザーにする必要がありますが、電話番号の番号を入力できます。 

### <a name="get-new-user-phone-numbers"></a>新しいユーザーの電話番号を取得します。 
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 左側のナビゲーションでは、**音声**に移動 > **電話番号**、**新しい番号を追加**をクリックして![[追加] ボタン](../images/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)、し、**新しいユーザーの番号**をクリックします。
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>ビジネス管理センターの Skype では使用できない新しい番号を取得します。
  
場合があります (国または地域) によってビジネス管理センターは、Skype を使用して、新規の番号を取得することはできません。 この例では、フォームをダウンロードし、私たちに送信する必要があります。 新しいユーザーの番号を要求する方法について[、組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>サービス プロバイダーまたは電話のキャリアからのポートまたは転送の電話番号
  
- ユーザー用に必要な電話番号が 999 個以下であれば、Skype for Business 管理センターの **新しい電話番号のポート注文**ウィザードを使用できます。 については、オンライン ビジネスの上で自分の電話番号を Skype に転送するのには[Office 365 に電話番号を転送](..//what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)する手順に従います。
    
- 999 を超える数の電話番号のポートが必要な場合は、ポート注文サービスの要求またはすべての Office 365 に移植されたこれらの電話番号を取得する順序を送信するのには[、組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。 

**新しい電話番号を取得するか、既存の番号を転送する方法の詳細については、[組織の電話番号の管理](../what-are-calling-plans-in-office-365\manage-phone-numbers-for-your-organization\manage-phone-numbers-for-your-organization.md)を参照してください。**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 4: サービスの電話番号 (電話会議、通話キュー、自動応答) を取得します。

Office 365 から、ユーザーの電話番号を取得するだけでなく検索し、有料またはオーディオの会議 (会議ブリッジ) の自動応答、および呼び出しキュー (サービス番号とも呼ばれます) などのサービスの無料電話番号を取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。 などのサービス数 100 コールの同時に処理できます、ユーザーの電話番号で、いくつかの呼び出しを同時に処理のみことができますが。

### <a name="get-new-service-numbers"></a>新しいサービス番号を取得する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 左側のナビゲーションでは、**音声**に移動 > **電話番号** > **新しい番号を追加**し、**新しいサービスの番号**をクリックします。
    
    > [!IMPORTANT] 
    > ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>ビジネス管理センターの Skype では使用できない新しい番号を取得します。
  
場合があります (国または地域) によってビジネス管理センターは、Skype を使用して、新規の番号を取得することはできません。 この例では、フォームをダウンロードし、私たちに送信する必要があります。 新しい番号を要求する方法について[、組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。 

### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトにポートの順序を手動で送信する必要があります。 種類ごとにサービスの番号 (フリー ダイヤルとダイヤル)、転送される、文字の承認 (ロード) を使用して別のポートの注文を送信する必要があります。 文字の承認 (ロード)、適切な種類のサービス番号を選択する必要があります。 マイクロソフト サポートに問い合わせる場合は、サービス番号 (*および数値以外のユーザーまたはサブスクライバー*) を転送すること、または十分コール ボリュームを処理するために同時の呼び出し元の容量ではありませんを指定するか確認してください。 電話番号を転送したり、自分の電話番号を持つ他の操作をする場合は、[組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>手順 5: プランの呼び出しを設定する場合は、

取得した電話番号は (手順 3)、ユーザーのため、呼び出し元の計画と、既に購入している電話システムとライセンス、および呼び出しの計画 (手順 2) に割り当てられている手順を実行されている場合は、部分的に設定されています。 プランの呼び出しのセットアップを完了するのには、次の 3 つの手順に従います。

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>緊急時のアドレスと、組織の場所を追加します。

1. **緊急の場所**を選択して [**音声**] ページで、 > **新しいアドレスを追加**します。
    
2. [ **新しい住所**] ウィンドウで、住所の名前を入力し、残りのボックスの入力を完了します。
    
     ![When you enter a new emergency address, the formatting of the street name might cause an error.](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > 上の図のように、英語圏のお客様で街路名が数字の場合は、必ず末尾に「st」または「th」を付けます。 
  
3. [ **検証**] を選択します。
    
    必要な場合は、住所の訂正を求められます。 
    
    > [!CAUTION]
    > 住所または公的アドレスの検証では、住所が正規の住所で、形式が正しいことが確認されます。 緊急アドレスは部分的に正しいなど、市区町村の名前を誤って入力する場合と渡すことがまだ検証が可能です。 誤記があっても検証をパスした場合、誤記がある市区町村名と住所の他の正しい部分の組み合わせによって、適切な緊急派遣センターに通話をルーティングするために十分な情報になります。 
  
    > [!TIP]
    > 緊急応答用に住所に修正が必要な場合は、住所が更新されたことを通知する緑色のバナーが表示されます。 
  
4. 住所が検証されたら、[ **保存**] を選びます。
    
### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>ユーザーに電話番号と緊急対応の住所を割り当てる

> [!TIP]
> この手順を実行する直前にさらにユーザーを追加すると、[ **音声ユーザー**] ページにユーザーが表示されるまでに **数時間** かかることがあります。これには遅延時間があります。
  
1. **ボイス ユーザー**ページで、電話番号と緊急時のアドレスを割り当てたいユーザーを選択します。
    
2. [操作] ウィンドウで、**割り当てる番号**をクリックします。
    
3. **番号の割り当て**] ページで、**割り当てる番号の選択**] ボックスの一覧で、ユーザーの電話番号を選択します。
    
4. 緊急アドレスを選択するには、都市の名前をボックスに入力し、**検索**を選択します。
    
    > [!IMPORTANT]
    > 米国外である場合、数値既に緊急アドレスでは、ですが、ここで変更することができます。 「[ユーザーの緊急対応の住所を割り当てるまたは変更する](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md)」をご覧ください。 
  
5. 電話番号と緊急対応の住所の両方を割り当てたら、[ **保存**] を選びます。
    
### <a name="tell-your-users-about-their-new-phone-numbers"></a>に関する新しい電話番号をユーザーに連絡します。


新しい電話番号をユーザーに通知する場合は、メールを送信するか、または各組織が指定する方法で行うことをお勧めします。 

以下は、**ビジネスの Skype**アプリでは、その電話番号を表示できる方法です。
  
1. デスクトップで Skype for Business にサインインします。
    
2. Choose **Settings** > **Tools** > **Options**. 
    
     ![To view your phone number, go to Settings > Tools > Options.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. 次に、[ **電話**] を選びます。 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
**マイクロソフトのチーム**では、ユーザーは、左側のナビゲーションで**の呼び出し**をクリックすると、その電話番号を表示できます。 電話番号は、ダイヤル パッドの上に表示されます。

![ユーザーは、左側のナビゲーションでの呼び出しをクリックすると、マイクロソフトのチームで、番号を確認できます。](../images/teams-phone-number.png)

**呼び出す計画を設定する手順のすべての詳細については、[計画を呼び出す設定](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)を参照してください。**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>手順 6: オーディオ会議を設定する場合は、

自分の組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 Skype ビジネスおよびマイクロソフトのチームには、これだけのオーディオ会議機能を搭載! 人は、ビジネスまたはマイクロソフトのチームのアプリケーションをモバイル デバイスまたは PC 上で、Skype を使用する代わりに、電話を使用するビジネスまたはマイクロソフトのチームの会議、Skype を呼び出すことができます。 
  
のみ、スケジュールや会議を計画している人の電話会議を設定する必要があります。 ダイヤルイン会議の参加者、ライセンスを取得、またはその他の設定に割り当てられている必要はありません。
  
オーディオ会議についてよく寄せられる質問は、[オーディオ会議のよく寄せられる質問](../audio-conferencing-in-office-365/audio-conferencing-common-questions.md)を参照してください。
    
1. **オーディオ会議**のアドオン ライセンスおよび通信のクレジットのライセンスを購入した場合も割り当てます。 手順については、[ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。

    オーディオ会議プロバイダーを決定します。 オーディオ会議プロバイダーは、オーディオ会議ブリッジを提供します。 会議用ブリッジは、ダイヤルインの電話番号、Pin、および会議の会議 Id を設定します。 Microsoft またはサード パーティ製のオーディオ会議プロバイダーを使用するかどうかを決定します。 

    > [!NOTE]
    > マイクロソフトのチームのユーザーには、サード ・ パーティ製のオーディオ会議プロバイダーのユーザーことはできません。 
  
    - **オーディオ会議プロバイダーとして Microsoft**: オーディオ会議の最も簡単なソリューションをする場合は、オーディオ会議プロバイダーとして Microsoft を選択します。
    
    - **オーディオ会議プロバイダーとして、サード パーティ製**: サード ・ パーティ製のオーディオを選択する場合、Office 365 での音声会議を使用できないための場所では、優れたサービスの品質はありません、既存の契約がある国で、会議プロバイダーです。 プロバイダーを検索するには、[マイクロソフトの特定](http://go.microsoft.com/fwlink/?LinkId=797530)に移動します。
 
2.  人が発生したり、会議をスケジュールするには、オーディオ会議プロバイダーを割り当てます。 [オーディオ会議プロバイダーとしてのマイクロソフトの割り当て](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)を参照してください。

3. 会議出席依頼を設定します。 次の手順は省略可能ですが、管理者の多くが実行するために。 
  
    1. [ミーティングの招待状をカスタマイズ](../set-up-skype-for-business-online/customize-meeting-invitations.md)します。 ユーザーに設定されているダイヤルの番号は、出席者に送信される会議出席依頼に自動的に追加されます。 ただし、独自のヘルプおよび法律上のリンク、テキスト メッセージ、および小規模な会社のグラフィックを追加することができます。
    
    2. [ミーティングの開催者の招待に収録されている電話会議の電話番号を設定](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)します。 これは、ユーザーがスケジュールされている会議で表示される電話番号です。
    
    3. [オーディオ会議の自動応答の言語設定](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)で、電話会議の電話番号にダイヤルするときに、呼び出し元を呼びかけられるように設定するのには、オーディオ会議自動アテンダントを使用します。 この手順は、Microsoft のオーディオのプロバイダーとして使用する場合にのみ適用されます。
    
    4. [オーディオ会議の会議の暗証番号 (pin) の長さを設定](../audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings.md)します。
    
    > [!NOTE]
    > この機能はまだ顧客に利用可能な Office 365 を使用して運用している中国で 21Vianet。 詳細については、 [21Vianet によって運営されて Office 365 について](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)を参照してください。 

**オーディオ会議の詳細については、[電話会議の設定](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)を参照してください。**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>手順 7: 電話システム コールのキューを設定する場合は、

電話システム キューには、保留中の呼び出しを自動的に配置する機能などを検索する人の中に呼び出しを処理するために次の呼び出しを使用可能なエージェントの機能の電話番号への呼び出し際に使用するあいさつ文が含まれています。呼び出しが保留中の音楽をリッスンしています。 組織の 1 つまたは複数の呼び出しキューを作成します。

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. 有料または無料のサービスの電話番号を取得した後が表示されます**ビジネス管理センターの Skype** > **音声** > **電話番号**と**番号の種類**の一覧には、無料**サービスとして一覧表示されます**. サービス番号を取得するには、 [Skype のビジネスおよびマイクロソフトのチームの取得サービスの電話番号](getting-service-phone-numbers.md)を参照するか、転送し、既存のサービス番号にする場合は、 [Office 365 に電話番号を転送する](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)を参照してください。
  
> [!NOTE]
> 米国以外のユーザーは、サービス番号を取得するビジネス管理センターの Skype を使うことはできません。 [組織の電話番号を管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する代わりに、米国の外側から行う方法を参照してください。

**Skype**で、新しい呼び出しキューを作成するに**呼のルーティング**] をクリックします > **キューを呼び出す**と、**新規追加**] をクリックし、指示に従って、[電話システム呼び出しキューを作成する]( create-a-phone-system-call-queue.md#step-3---create-a-new-call-queue)は、**手順 3**にします。

**呼び出しキューの詳細については、[電話システムの呼び出しキューを作成する](create-a-phone-system-call-queue.md)を参照してください。**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>手順 8: 電話システムを設定する場合は、自動的に応答

自動応答は、組織へのコールし、右の部門にそれらを取得するには、キュー、人、または演算子を呼び出すメニュー システムを移動するユーザーを使用できます。 ビジネス管理センターは、Skype を使用して、組織の自動応答を作成できます。 

作成する新しい自動アテンダントでは、ビジネス管理センターの Skype で**呼のルーティング**] をクリックします > **自動応答**では、**新規追加**] をクリックし、指示に従って、電話システムの自動の[セットの**ステップ 2**では、各ページのアテンダント](set-up-a-phone-system-auto-attendant.md#step-2---create-a-new-auto-attendant)。

**電話システムの自動応答の詳細については、[電話システムの自動応答の設定](set-up-a-phone-system-auto-attendant.md)を参照してください。**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 9: サービスの電話番号 (電話会議、通話キュー、自動応答) を割り当てる

**上記の手順 4**から、サービスの番号を作成したらは、使用するサービスの種類ごとに割り当てる必要があります。 専用のサービスの電話番号を挿入する場合など、(有料またはフリー ダイヤル)、会議用ブリッジに番号を割り当てるには必要です。

- オーディオ会議では、割り当てることができます専用番号会議用ブリッジを**Office 365 の管理センター**に移動して > **管理センター** > **ビジネス用の Skype** > **電話会議**をクリックして、会議ブリッジまたは[有料または、オーディオ会議ブリッジ上のフリー ダイヤル番号を変更する](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)を参照しています。

- 自動応答を割り当てることができます専用番号自動アテンダントを**Office 365 の管理センター**に移動して > **管理センター** > **ビジネス用の Skype** > **呼のルーティング** > **自動応答**[自動応答] をクリックします。 サービス番号に**電話番号**が表示されますが既にある [**全般**] ページのドロップダウン リストにします。 詳細については、[電話システムの自動応答の設定](set-up-a-phone-system-auto-attendant.md)を参照してください。

- キューの呼び出しに割り当てることができます専用番号呼び出しキューを**Office 365 の管理センター**に移動して > **管理センター** > **ビジネス用の Skype** > **呼のルーティング** > **キューを呼び出す**とをクリックします。呼び出しキューです。 サービス番号に**電話番号**が表示されますが既にある [**全般**] ページのドロップダウン リストにします。 詳細については、[電話システムの呼び出しキューを作成する](create-a-phone-system-call-queue.md)を参照してください。

**新しいサービスの番号を取得して、既存のサービス番号を移植する方法の詳細については、[サービスの電話番号の取得](getting-service-phone-numbers.md)を参照してください。**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>通信のクレジット、組織の設定手順 10。

[] Skype for Business および Microsoft Teams で無料電話番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。 また、 **任意の発信先** にダイヤルアウトする機能が必要な、通話プラン (国内および国際通話) ユーザーと電話会議ユーザー向けにコミュニケーション クレジットを設定することをお勧めします。 ご利用の通話プランまたは電話会議のサブスクリプションでは、多くの国や地域が含まれていますが、一部の発信先が含まれていない可能性があります。 コミュニケーション クレジットの請求を設定しない場合や、ユーザーに **コミュニケーション クレジット**のライセンスを割り当てない場合に (国/地域の通話プランまたは電話会議プランに基づき) 組織の通話分数が不足すると、これらのユーザーは通話を発信することや、電話会議からダイヤルアウトすることができなくなります。 読み取ることによって資金調達の金額は、推奨などの詳細を取得することができます、[通信のクレジットは何ですか?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> 費用を確認するには、[こちらで料金をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。 

### <a name="to-set-up-communications-credits"></a>通信のクレジットを設定するには 

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add-ons** > **Buy add-ons**, and then choose **Communications Credits** > **Buy now**.
    
3. **通信のクレジット**申し込みのページでの情報を入力し、[**次へ**] をクリックします。
        
4. 支払い情報を入力して、[ **注文**] をクリックします。
    >[!IMPORTANT]
    >ボリューム ライセンス契約の場合は、支払のエンタープライズ契約番号を選択する可能性があります。 エンタープライズ契約番号が複数ある場合は、支払に使用するには、エンタープライズ アグリーメントを選択することができます。 エンタープライズ ライセンス契約番号 (存在する場合) に関連付けるには、発注書番号を指定することを指定するもされます。
    
**通信のクレジットの設定に関する詳細については、[組織の通信のクレジットを設定](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)を参照してください。**
  
### <a name="assign-a-communications-credits-license-to-users"></a>通信のクレジットのライセンスをユーザーに割り当てる

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. In the left navigation of the Office 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.
    
3. 操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。
    
4. On the **Product licenses** page, toggle ** Communications Credits** to **On** to assign this license, and then click **Save**.
    
    > [!NOTE]
    > **Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、この手順を行うことをお勧めします。

**通信のクレジットのライセンスの割り当ての詳細については、[組織の通信のクレジットの設定](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)を参照してください。**

## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。
[Office 365 での電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 