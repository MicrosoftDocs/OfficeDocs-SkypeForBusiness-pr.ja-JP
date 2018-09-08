---
title: 組織内の電話システムの設定
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '組織の電話システム (PBX をクラウド) を設定する方法について説明します。 '
ms.openlocfilehash: 54ac25bb3c2ec88a35bc8e017f7a3eb2e55edc1e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883238"
---
# <a name="setting-up-phone-system-in-your-organization"></a>組織内の電話システムの設定

Office 365 の電話システムを設定するためのステップ バイ ステップ ガイドは以下のとおりです。 各手順の最後に、詳細な追加情報へのリンクを利用できます。

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>ステップ 1: 電話システムは、国または地域で利用可能なことを確認します。

1.  最初に [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) へ進み、ページの上部にある一覧表から国または地域を選択します。 
2.   **電話システム** での機能と詳細の一覧を確認します。 
3.  電話システムが使用可能な場合は、手順 2 に進みます。 

**電話システムおよびオーディオ会議の地域別利用可能時間に関する詳細については、 [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) を参照してください。**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>手順 2: 電話システムおよび通話プランのライセンスを購入し、割り当てる

電話システムと通話プランのライセンスを 1 人のユーザーに割り当てるには、Office 365 のライセンスを割り当てるのと同じ手順をとります。 「[Skype for Business と Microsoft Teams のライセンスを割り当てる](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」をご覧ください。 一括で複数のユーザーを割り当てる場合は、 [Skype for Business と Microsoft Teams のライセンスを割り当てる](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) を参照してください。

## <a name="step-3-get-phone-numbers-for-your-users"></a>手順 3: ユーザーの電話番号を取得します。

[] 組織内でユーザーが電話を発着信できるように設定するには、組織のための電話番号を取得する必要があります。

ユーザーに番号を取得する 3 つの方法があります。
- Skype for Business 管理センターを使用して、新しい電話番号を取得する。
- Skype for Business管理センターでは使用できない、新しい番号を取得します。
- 現在のサービス プロバイダーまたは携帯電話会社から Office 365 に既存の番号を移行する。

[ **新しいユーザー番号を追加**] ページを使用して、電話番号の確認、検索、取得、予約を行う必要があります。 [ 国または地域]、[ 都道府県]、[ 市区町村] で検索してから、ユーザー用に必要となる電話番号の数を入力できます。

### <a name="get-new-user-phone-numbers"></a>新しいユーザーの電話番号を取得します。 
 
![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. ** [Office 365 管理センター] ** > ** [Skype for Business]** に移動します。
    
3. 左側のナビゲーションでは、**音声**に移動 > **電話番号**、**新しい番号を追加**をクリックして![[追加] ボタン](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)、し、**新しいユーザーの番号**をクリックします。
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Skype for Business管理センターでは使用できない、新しい番号を取得します。
  
場合があります (国または地域) によってビジネス管理センターは、Skype を使用して、新規の番号を取得することはできません。 この例では、フォームをダウンロードし、私たちに送信する必要があります。 新しいユーザーの番号を要求する方法については、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>使用中のサービス プロバイダーまたは携帯電話会社から電話番号を移行する
  
- ユーザー用に必要な電話番号が 999 個以下であれば、Skype for Business 管理センターの **新しい電話番号のポート注文**ウィザードを使用できます。 については、オンライン ビジネスの上で自分の電話番号を Skype に転送するのには[Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)する手順に従います。
    
- 999 を超える数の電話番号のポートが必要な場合は、ポート注文サービスの要求またはすべての Office 365 に移植されたこれらの電話番号を取得する順序を送信するのには[、組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。 

**新しい電話番号を取得するか、既存の番号を転送する方法の詳細については、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 4: サービス用の電話番号 (電話会議、通話キュー、自動応答) を取得します。

Office 365 から、ユーザーの電話番号を取得するだけでなく検索し、有料またはオーディオの会議 (会議ブリッジ) の自動応答、および呼び出しキュー (サービス番号とも呼ばれます) などのサービスの無料電話番号を取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。 などのサービス数 100 コールの同時に処理できます、ユーザーの電話番号で、いくつかの呼び出しを同時に処理のみことができますが。

### <a name="get-new-service-numbers"></a>新しいサービス番号を取得する

![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**


1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. ** [Office 365 管理センター] ** > ** [Skype for Business]** に移動します。

3. 左側のナビゲーションでは、**音声**に移動 > **電話番号** > **新しい番号を追加**し、**新しいサービスの番号**をクリックします。

    > [!IMPORTANT]
    > ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Skype for Business管理センターでは使用できない、新しい番号を取得します。
  
場合があります (国または地域) によってビジネス管理センターは、Skype を使用して、新規の番号を取得することはできません。 この例では、フォームをダウンロードし、私たちに送信する必要があります。 新しいユーザーの番号を要求する方法については、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。 

### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトに番号移行注文を手動で提出する必要があります。 承認状（LOA)を使用して、移行したいサービス番号（有料・無料）の種類ごとに各々番号移行注文を提出する必要があります。 承認状（LOA)では、適切な種類のサービス番号を選択する必要があります。 マイクロソフト サポートに問い合わせる場合は、サービス番号 (*ユーザーまたはサブスクライバーの番号ではなく*) を転送すること、または通話量に対応するための同時通話許容量が十分ではないことを指定してください。 電話番号を転送したり、自分の電話番号で他の操作をする場合は、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>手順 5: 通話プランを設定する場合

上記の手順に従っていれば、あなたはすでに電話システムとライセンス、通話プラン（手順２）を購入して割り当てられ、ユーザー用の電話番号を取得（手順３）したことになるので、あなたの通話プランは部分的に設定されています。
 通話プランのセットアップを完了するのには、次の 3 つの手順に従います。

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>緊急時のアドレスと、組織の場所を追加します。

1. **緊急の場所**を選択して [**音声**] ページで、 > **新しいアドレスを追加**します。

2. [ **新しい住所**] ウィンドウで、住所の名前を入力し、残りのボックスの入力を完了します。
    
     ![新しい緊急時のアドレスを入力すると、住所の書式設定がエラーを引き起こす可能性があります。](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
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

2. [操作] ウィンドウで、 **割り当てる番号** をクリックします。

3. **番号の割り当て**] ページで、**割り当てる番号の選択**] ボックスの一覧で、ユーザーの電話番号を選択します。

4. 緊急アドレスを選択するには、都市の名前をボックスに入力し、**検索**を選択します。

    > [!IMPORTANT]
    > 米国外である場合、数値既に緊急アドレスでは、ですが、ここで変更することができます。 「[ユーザーの緊急対応の住所を割り当てるまたは変更する](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)」をご覧ください。 
  
5. 電話番号と緊急対応の住所の両方を割り当てたら、[ **保存**] を選びます。

### <a name="tell-your-users-about-their-new-phone-numbers"></a>に関する新しい電話番号をユーザーに連絡します。


新しい電話番号をユーザーに通知する場合は、メールを送信するか、または各組織が指定する方法で行うことをお勧めします。

以下は、**ビジネスの Skype**アプリでは、その電話番号を表示できる方法です。

1. デスクトップで Skype for Business にサインインします。
    
2.  **Settings** > **Tools** > **Options** を選択します。 
    
     ![電話番号を表示するには、設定 > ツール > オプション。](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. 次に、[ **電話**] を選びます。 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
 **マイクロソフトのチーム**では、ユーザーは、左側のナビゲーションで **呼び出し** をクリックすると、その電話番号を表示できます。 電話番号は、ダイヤル パッドの上に表示されます。

![ユーザーは、左側のナビゲーションで呼び出しをクリックすると、Microsoft Teams で番号を確認できます。](media/teams-phone-number.png)

**通話プランを設定する手順すべての詳細については、 [通話プランの設定](set-up-calling-plans.md) を参照してください。**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>手順 6: 電話会議を設定する場合

自分の組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 Skype ビジネスおよびマイクロソフトのチームには、これだけのオーディオ会議機能を搭載! 人は、ビジネスまたはマイクロソフトのチームのアプリケーションをモバイル デバイスまたは PC 上で、Skype を使用する代わりに、電話を使用するビジネスまたはマイクロソフトのチームの会議、Skype を呼び出すことができます。

のみ、スケジュールや会議を計画している人の電話会議を設定する必要があります。 ダイヤルインする会議参加者には、割り当てられたライセンスやその他のセットアップは必要ありません。
  
電話会議についてよく寄せられる質問については、 [電話会議についてよくある質問](audio-conferencing-common-questions.md) を参照してください。
    
1.  **電話会議** アドオンライセンスとコミュニケーション クレジットライセンスを購入した場合は、それらも割り当てます。 手順については、[ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)を参照してください。

    電話会議のプロバイダーを決定します。 電話会議プロバイダーは、電話会議ブリッジを提供します。 会議用ブリッジは、ダイヤルインの電話番号、Pin、および会議の会議 Id を設定します。 Microsoft を使用するか、Microsoft以外の電話会議プロバイダーを使用するかを決定します。

    > [!NOTE]
    > Microsoft Teams のユーザーには、Microsoft 以外の電話会議プロバイダーを使うことはできません。

    - **電話会議プロバイダーとしての Microsoft**: 電話会議の最も簡単なソリューションをお求めなら、電話会議プロバイダーとして Microsoft を選択します。
    
    - **オーディオ会議プロバイダーとして、サード パーティ製**: サード ・ パーティ製のオーディオを選択する場合、Office 365 での音声会議を使用できないための場所では、優れたサービスの品質はありません、既存の契約がある国で、会議プロバイダーです。 プロバイダーを検索するには、 [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530) に進みます。
 
2.  会議を主導したり、会議の日程を立てる人達に電話会議プロバイダーを割り当てます。 [オーディオ会議プロバイダーとしてのマイクロソフトの割り当て](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)を参照してください。

3. 会議出席依頼を設定します。 次の手順はオプションですが、管理者の多くは次の設定を行うのを好みます。 
  
    1. [ビジネス用の Skype でミーティングの招待状をカスタマイズ](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)します。 ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議出席依頼に自動的に追加されます。 ただし、独自のヘルプや法的リンク、テキスト メッセージ、会社の小さな画像を追加できます。
    
    2. [ビジネス用の Skype](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)または[マイクロソフトのチームで](set-the-phone-numbers-included-on-invites-in-teams.md)ミーティングの開催者に含まれているへの招待には、電話会議の電話番号を設定します。 これは、ユーザーが開催を予定している会議で表示される電話番号です。
    
    3. [ビジネス用の Skype で](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing)電話会議、または[マイクロソフトのチームで](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)の電話会議の電話番号にダイヤルするときに、呼び出し元を呼びかけられるように設定するのには、オーディオ会議自動アテンダントを使用するには、自動アテンダントの言語を設定します。 この手順は、Microsoft を電話会議プロバイダーとして使用している場合にのみ適用されます。
    
    4. オーディオ会議の会議の暗証番号 (pin) の長さを設定する[ビジネス用の Skype](/skypeforbusiness/audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings)または[マイクロソフトのチームで](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)。
    
    > [!NOTE]
    > 中国の 21Vianet で運用される Office 365 を使用している顧客は、まだこの機能を使用できません。 詳細については、 [21Vianet で運用される Office 365 について](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE) を参照してください。

**電話会議の詳細については、 [電話会議の設定](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) を参照してください。**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>手順 7: 電話システムの通話キューを設定する場合

電話システム キューには、保留中の呼び出しを自動的に配置する機能などを検索する人の中に呼び出しを処理するために次の呼び出しを使用可能なエージェントの機能の電話番号への呼び出し際に使用するあいさつ文が含まれています。呼び出しが保留中の音楽をリッスンしています。 組織の 1 つまたは複数の呼び出しキューを作成します。

通話キューを作成し設定する前に、既存の有料または無料のサービス番号を取得もしくは転送する必要があります。 有料または無料のサービスの電話番号を取得した後、  **Skype for Business 管理センター** > **音声** > **電話番号** に番号が表示され、  **番号の種類** のリストには、 **サービスー無料** として一覧表示されます。 サービス番号を取得するには、  [Skype for Business と Microsoft Teams 用のサービス電話番号の取得](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) を参照するか、既存のサービス番号を転送する場合は、  [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md) を参照してください。
  
> [!NOTE]
> 米国以外のユーザーは、サービス番号を取得するビジネス管理センターの Skype を使うことはできません。 [組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する代わりに、米国の外側から行う方法を参照してください。

  **Skype for Business 管理センター** で、新しい通話キューを作成するには、 **通話ルーティング** > **通話キュー** をクリックし、  **新規追加** をクリックし、 [電話システム呼び出しキューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue) の  **手順 3** の指示に従います。

**通話キューの詳細については、 [電話システムの通話キューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue) を参照してください。**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>手順 8: 自動応答電話システムを設定する場合

自動応答は、組織へのコールし、右の部門にそれらを取得するには、キュー、人、または演算子を呼び出すメニュー システムを移動するユーザーを使用できます。 ビジネス管理センターは、Skype を使用して、組織の自動応答を作成できます。

Skype for Business 管理センターで、新しい自動応答を作成するには、 **通話ルーティング** > **自動応答** をクリックし、 **新規追加**をクリックし、 [自動応答電話システム設定](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant) の **ステップ 2** の指示に従って下さい。

**電話システムの自動応答の詳細については、 [電話システムの自動応答の設定](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) を参照してください。**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 9: サービス用電話番号 (電話会議、通話キュー、自動応答) の割り当て

 **上記の手順 4** から、サービスの番号を作成したら、使用するサービスの種類ごとに番号を割り当てる必要があります。 専用のサービスの電話番号(有料またはフリー ダイヤル)を挿入する場合などは、会議用ブリッジに番号を割り当てる必要があります。

- 電話会議用に専用番号を会議用ブリッジに割り当てることができます。それには、 **Office 365 の管理センター** > **管理センター** > **Skype for Business** > **電話会議** に進み、会議ブリッジをクリックするか、 [電話会議ブリッジ上の有料・無料番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md) を参照してください。

- 自動応答では、自動アテンダントに専用番号を割り当てることができます。それには、  **Office 365 の管理センター** > **管理センター** > **Skype for Business** > **通話ルーティング** > **自動応答** に進み、自動応答 をクリックします。 既存のサービス番号は、 **全般** ページの **電話番号** ドロップダウンのリストに表示されます。 詳細については、  [電話システムの自動応答の設定](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) を参照してください。

- 通話キューでは、通話キューに専用番号を割り当てることができます。それには、  **Office 365 の管理センター** > **管理センター** > **Skype for Business** > **通話ルーティング** > **通話キュー** と進み、「通話キュー」をクリックします。 既存のサービス番号は、 **全般** ページの **電話番号** ドロップダウンのリストに表示されます。 詳細については、 [電話システムの通話キューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue) を参照してください。

**新しいサービス番号を取得し、既存のサービス番号を転送する方法の詳細については、 [サービスの電話番号の取得](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)  を参照してください。**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>通信のクレジット、組織の設定手順 10。

[] Skype for Business および Microsoft Teams で無料電話番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。 また、 **任意の発信先** にダイヤルアウトする機能が必要な、通話プラン (国内および国際通話) ユーザーと電話会議ユーザー向けにコミュニケーション クレジットを設定することをお勧めします。 ご利用の通話プランまたは電話会議のサブスクリプションでは、多くの国や地域が含まれていますが、一部の発信先が含まれていない可能性があります。 コミュニケーション クレジットの請求を設定しない場合や、ユーザーに **コミュニケーション クレジット**のライセンスを割り当てない場合に (国/地域の通話プランまたは電話会議プランに基づき) 組織の通話分数が不足すると、これらのユーザーは通話を発信することや、電話会議からダイヤルアウトすることができなくなります。 読み取ることによって資金調達の金額は、推奨などの詳細を取得することができます、[通信のクレジットは何ですか?](what-are-communications-credits.md)
  
> [!NOTE]
> 費用を確認するには、[こちらで料金をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。

### <a name="to-set-up-communications-credits"></a>通信のクレジットを設定するには

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. Office 365 管理ページ左側のナビゲーションで  **請求** > **サブスクリプション** > **アドオン** > **アドオンの購入** に進み、 **コミュニケーションクレジット** > **今すぐ購入** を選択してください。

3. **通信のクレジット**申し込みのページでの情報を入力し、[**次へ**] をクリックします。

4. 支払い情報を入力して、[ **注文**] をクリックします。
    >[!IMPORTANT]
    >一括ライセンス契約の場合は、支払いにエンタープライズ契約番号を選択できます。 エンタープライズ契約番号が複数ある場合は、どのエンタープライズ アグリーメントを支払いに使用するかを選択することができます。 エンタープライズ 契約番号 (存在する場合) に関連付けるよう、特定の発注書番号を指定することもできます。
    
**コミュニケーションクレジットの設定に関する詳細については、 [組織のコミュニケーションクレジットを設定](set-up-communications-credits-for-your-organization.md) を参照してください。**
  
### <a name="assign-a-communications-credits-license-to-users"></a>通信のクレジットのライセンスをユーザーに割り当てる

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. Office 365 管理ページの左側のナビゲーションで、 **ユーザー** > **アクティブなユーザー** に進み、そのリストから一人、または複数のユーザーを選択します。

3. 操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。

4. [**製品ライセンス**] ページで、**上**、本ライセンスを割り当てるには、**通信のクレジット**を切り替えるし、[**保存**] をクリックします。

    > [!NOTE]
    > **Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、この手順を行うことをお勧めします。

**コミュニケーションクレジットのライセンスの割り当ての詳細については、 [組織用コミュニケーションクレジットの設定](set-up-communications-credits-for-your-organization.md) を参照してください。**

## <a name="related-topics"></a>関連トピック
[Office 365 での電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
