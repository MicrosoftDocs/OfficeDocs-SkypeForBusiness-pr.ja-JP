---
title: 組織内の電話システムの設定
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
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
- Phone System
description: '組織の電話システム (クラウド PBX) の設定方法について説明します。 '
ms.openlocfilehash: 304bdc58f8f2e077aa58dc4ded46f55387392374
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588176"
---
# <a name="setting-up-phone-system-in-your-organization"></a>組織内の電話システムの設定

以下は、Office 365 で電話システムを設定するための手順ガイドです。各手順の最後に、追加の詳細情報へのリンクが提供されています。

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>ステップ 1: 電話システムは、国または地域で利用可能なことを確認します。

1.  最初に [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) へ進み、ページの上部にある一覧表から国または地域を選択します。 
2.   **電話システム** での機能と詳細の一覧を確認します。 
3.  電話システムが使用可能な場合は、手順 2 に進みます。 

**電話システムおよびオーディオ会議の地域別利用可能時間に関する詳細については、 [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) を参照してください。**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>手順 2: 電話システムおよび通話プランのライセンスを購入し、割り当てる

電話システムと通話プランのライセンスを 1 人のユーザーに割り当てるには、Office 365 ライセンスの割り当ての手順と同じです。「[Microsoft Teams ライセンスを割り当てる](assign-teams-licenses.md)」を参照してください。複数のユーザーをまとめて割り当てる場合は、「[Microsoft Teams ライセンスを割り当てる](assign-teams-licenses.md)」を参照してください。

## <a name="step-3-get-phone-numbers-for-your-users"></a>ステップ 3: ユーザー向けの電話番号を取得する

組織内でユーザーを設定し、電話を掛けたり受けたりする前に、ユーザーの電話番号を取得する必要があります。

ユーザー用の番号を取得するには、次の 3 つの方法があります。
- Skype for Business 管理センターを使用して新しい番号を取得します。
- Skype for Business管理センターでは使用できない、新しい番号を取得します。
- 既存の番号を現在のサービス プロバイダーまたは電話会社から Office 365 に移行または転送します。

新しいユーザー番号を表示、検索、取得、および予約するには、[**新しいユーザー番号を追加**] ページを使用する必要があります。国/地域、都道府県、市区町村で検索し、ユーザー用に必要な電話番号の数を入力できます。

### <a name="get-new-user-phone-numbers"></a>新しいユーザー電話番号を取得する 
 
![](media/sfb-logo-30x30.png) **Skype for business 管理センターを使用し**た skype for business ロゴを示すアイコン

1. 職場または学校のアカウントを使用して、Microsoft 365 にサインインします。

2. **Microsoft 365 管理センター** > **Skype for Business** に移動します。
    
3. 左のナビゲーションで、[**音声** > **電話番号**] に**** ![移動し、[追加] ボタンをクリックしてプラス](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)記号として表示し、[**新しいユーザー番号**] をクリックします。
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Skype for Business管理センターでは使用できない、新しい番号を取得します。
  
ご利用国/地域によっては、Skype for Business 管理センターを使用して新しい番号を取得できない場合があります。その場合は、フォームをダウンロードし、記入したフォームを Microsoft に送付する必要があります。新しいユーザー番号をリクエストする方法の詳細については、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>サービス プロバイダーまたは電話会社から電話番号を移行または転送する
  
- 必要なユーザーの電話番号数が 999 以下である場合、Skype for Business 管理センターで**新しい電話番号のポート注文**ウィザードを使用できます。電話番号を Skype for Business Online に移動するには、「[Office 365 に電話番号を移動する](transfer-phone-numbers-to-office-365.md)」で説明する手順に従ってください。
    
- 電話番号が 999 個よりも多い電話番号を移行する必要がある場合は、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照して移行注文サービスの依頼または注文を発行し、Office 365 に移行される電話番号をすべて取得します。 

**新しい電話番号を取得するか、既存の番号を転送する方法の詳細については、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 4: サービス用の電話番号 (電話会議、通話キュー、自動応答) を取得します。

Office 365 ユーザー用の電話番号の取得に加え、電話会議 (会議ブリッジ用)、自動応答、通話キュー (別名: サービス番号) などのサービス用に、有料または無料電話番号を検索し、取得できます。ユーザーまたはサブスクライバーの電話番号に比べて、サービス電話番号はより高い同時通話の処理能力を持ちます。たとえば、ユーザーの電話番号 1 つが同時に取り扱える通話数はごく少数なのに対して、1 つのサービス番号は何百もの通話を同時に取り扱えます。

### <a name="get-new-service-numbers"></a>新しいサービス番号を取得する

![](media/sfb-logo-30x30.png) **Skype for business 管理センターを使用し**た skype for business ロゴを示すアイコン


1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Microsoft 365 管理センター** > **Skype for Business** に移動します。

3. In the left navigation go to **Voice** > **Phone numbers** > **Add** then click **New service numbers**.

    > [!IMPORTANT]
    > Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム**アドオン ライセンス、または**電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Skype for Business管理センターでは使用できない、新しい番号を取得します。
  
ご利用国/地域によっては、Skype for Business 管理センターを使用して新しい番号を取得できない場合があります。その場合は、フォームをダウンロードし、記入したフォームを Microsoft に送付する必要があります。新しい番号をリクエストする方法の詳細については、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。 

### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービス プロバイダーまたは通信事業者からサービス番号を移動する場合は、ポートの注文を手動で Microsoft に送信する必要があります。承認状 (LOA) を使用して、移動するサービス番号の種類 (有料電話番号または無料電話番号) ごとに別々のポート注文を送信する必要があります。承認状 (LOA) では、適切な種類のサービス番号が選択されている必要があります。Microsoft サポートに連絡する際は、移動する番号は*ユーザーまたはサブスクライバーの番号ではなく*、サービス番号であることを必ず指定してください。これを指定しない場合、実際の通話件数を処理するには同時通話処理能力が不十分なものになる可能性があります。電話番号の移動や電話番号に関するその他の手続きを行うには、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>手順 5: 通話プランを設定する場合

上記の手順を実行すると、電話システムと通話プランのライセンスの購入と割り当て (手順 2) およびユーザー用の電話番号の取得 (手順 3) が完了したことになり、通話プランのセットアップは部分的に完了しています。通話プランのセットアップを完了するには、次の 3 つの手順を実行してください。

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>組織の緊急連絡先と場所を追加する

1. [**音声**] ページで、[**緊急対応の場所**]  >  [**新しいアドレスを追加**] の順に選択します。

2. [**新しい住所**] ウィンドウで、住所の名前を入力し、残りのボックスに入力します。
    
     ![[新しい住所] ウィンドウのスクリーンショット](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > 上の図のように、英語圏のお客様で街路名が数字の場合は、必ず末尾に「st」または「th」を付けます。

3. [ **検証**] を選択します。

    必要な場合は、住所の訂正を求められます。

    > [!CAUTION]
    > 住所や番地を確認できるよう、正当な住所が正しい形式で入力されている必要があります。部分的に正しい緊急対応用の住所 (たとえば、市名の綴りが間違っていたなど) でも住所確認が取れる場合があります。綴りに間違いがあっても住所確認が取れた場合は、綴りの間違った市名と住所情報の他の部分を組み合わせることで、通話を適切な緊急出動センターにルーティングするのに十分な情報があることを意味します。

    > [!TIP]
    > 緊急応答用に住所に修正が必要な場合は、住所が更新されたことを通知する緑色のバナーが表示されます。

4. 住所が検証されたら、[ **保存**] を選びます。

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>ユーザーに電話番号と緊急連絡先を割り当てる

> [!TIP]
> この手順を実行する直前にさらにユーザーを追加すると、[ **音声ユーザー**] ページにユーザーが表示されるまでに **数時間** かかることがあります。これには遅延時間があります。

1. [**音声ユーザー**] ページで、電話番号と緊急連絡先を割り当てるユーザーを選択します。

2. [操作] ウィンドウで、 **割り当てる番号** をクリックします。

3. [**番号を割り当てる**] ページの [ **割り当てる番号を選択**] リストで、ユーザー用の電話番号を選択します。

4. 緊急連絡先を選ぶには、ボックスに市区町村の名前を入力し、[**検索**] を選択します。

    > [!IMPORTANT]
    > 米国以外の場合は電話番号に緊急対応の住所がすでに関連付けられていますが、この住所は変更できます。詳細については、「[ユーザーの緊急対応の住所の割り当てまたは変更](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)」を参照してください。 
  
5. 電話番号と緊急連絡先の両方を割り当てたら、[**保存**] を選択します。

### <a name="tell-your-users-about-their-new-phone-numbers"></a>新しい電話番号をユーザーに通知する


メールを送信するか、会社の適切な連絡方法を使用して、ユーザーに新しい電話番号を伝えることをお勧めします。

次に、ユーザーの **Skype for Business** アプリに電話番号がどのように表示されるかを示します。

1. デスクトップで Skype for Business にサインインします。
    
2.  **Settings** > **Tools** > **Options** を選択します。 
    
     ![[ツール] メニューの [オプション] のスクリーンショット](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. 次に、[ **電話**] を選びます。 
    
    ![Skype for Business 電話のオプションのスクリーンショット](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
**Microsoft Teams** では、ユーザーは左側のナビゲーションで [**通話**] をクリックすると、自分の電話番号を表示できます。電話番号はダイヤル パッドの上部に表示されます。

![[通話] をクリックした後に使用できるオプションのスクリーンショット](media/teams-phone-number.png)

**通話プランを設定する手順すべての詳細については、 [通話プランの設定](set-up-calling-plans.md) を参照してください。**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>手順 6: 電話会議を設定する場合

組織のメンバーが電話で会議に参加することが必要になる場合があります。Skype for Business と Microsoft Teams では、このようなシチュエーションで活用できる電話会議機能が提供されています。ユーザーは、モバイル デバイスや PC 上の Skype for Business アプリまたは Microsoft Teams アプリを使用することなく、電話を使用して Skype for Business または Microsoft Teams の会議に参加できます。

電話会議の設定は、会議のスケジュールを設定または会議を進行するユーザーに対してのみ必要です。ダイヤルインで参加するユーザーについては、ライセンスの割り当てや他の設定は必要ありません。
  
電話会議についてよく寄せられる質問については、 [電話会議についてよくある質問](audio-conferencing-common-questions.md) を参照してください。
    
1. **電話会議**アドオンのライセンスやコミュニケーション クレジットのライセンスを購入した場合は、これらも割り当てます。手順については、「[Microsoft Teams ライセンスを割り当てる](assign-teams-licenses.md)」を参照してください。

    電話会議のプロバイダーを決めます。電話会議のプロバイダーは、電話会議ブリッジを提供します。会議のダイヤルイン電話番号、PIN、および会議 ID は、会議ブリッジで設定されます。Microsoft とサード パーティの電話会議プロバイダーのどちらを使用するかを決めます。

    > [!NOTE]
    > Microsoft Teams のユーザーには、Microsoft 以外の電話会議プロバイダーを使うことはできません。

    - **電話会議プロバイダーとしての Microsoft**: 電話会議の最も簡単なソリューションをお求めなら、電話会議プロバイダーとして Microsoft を選択します。
    
    - **サード パーティの電話会議プロバイダーの使用**: Office 365 の電話会議が利用できない国の場合、サービスの品質が低い地域の場合、または既存の契約がある場合、サード パーティの電話会議プロバイダーを選択してください。プロバイダーを検索するには、 [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530) をご覧ください。
 
2. 会議を進行またはスケジュール設定するユーザーに、電話会議プロバイダーを割り当てます。詳細については、「[Microsoft を電話会議プロバイダーとして割り当てる](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)」を参照してください。

3. 会議の出席依頼を設定します。次の手順は省略可能ですが、多くの管理者は実行しています。 
  
   1. [Skype for Business の会議の出席依頼をカスタマイズします](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)。出席者に送信される会議の出席依頼には、ユーザーに設定されているダイヤルイン番号が自動的に追加されますが、独自のヘルプ、法的事項へのリンク、テキスト メッセージ、および小さな会社ロゴを追加できます。
    
   2. [Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) または [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) の招待状に記載される会議の開催者に、電話会議の電話番号を設定します。この電話番号は、ユーザーがスケジュールする会議に表示される電話番号です。
    
   3. [Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) または [Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) の電話会議での自動応答言語を設定します。これは、電話会議の電話番号にダイヤルインしてくる発信者への自動応答の挨拶で使用される言語です。この手順は、電話会議プロバーダーに Microsoft を使用している場合にのみ当てはまります。
    
   4. [Microsoft Teams で](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)電話会議用の PIN の長さを設定します。
    
      > [!NOTE]
      > この機能は、21Vianet が運営する Office 365 を中国で使用しているお客様にはまだご利用いただけません。詳細については、「 [21Vianet が運営する Office 365 について](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)」を参照してください。

**電話会議の詳細については、「[Microsoft Teams の電話会議を設定する](set-up-audio-conferencing-in-teams.md)」を参照してください。**

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>手順 7: クラウドの通話キューを設定する場合

クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。

通話キューを作成または設定できるようにするには、既存の有料または無料サービス番号を取得または移動する必要があります。有料または無料サービス番号を取得すると、**Skype for Business 管理センター**  >  [**音声**]  >  [**電話番号**] に表示され、[**番号の種類**] は [**サービス - フリー ダイヤル**] と表示されます。サービス番号を取得する方法については、「[Skype for Business および Microsoft Teams のサービス電話番号の取得](/microsoftteams/getting-service-phone-numbers)」を参照し、既存のサービス番号を移す場合は「[Office 365 に電話番号を移動する](transfer-phone-numbers-to-office-365.md)」を参照してください。
  
> [!NOTE]
> 米国以外の場合は、サービス番号を取得するのに Skype for Business 管理センターを使用できません。米国以外の場所でサービス番号を取得する方法については、「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。

[**Skype for Business 管理センター**] で、新しい通話キューを作成するには、[**通話ルーティング**]  >  [**通話キュー**]、そして [**新規追加**] をクリックし、「[クラウド呼び出しキューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue)」 の**手順 3** の指示に従います。

**通話キューの詳細については、[[クラウド通話キューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)] を参照してください。**

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>手順 8: クラウドの自動応答を設定する場合

自動応答は、組織に電話をかけてくる方にメニュー システムを案内し、目的の部署、通話キュー、担当者、またはオペレーターにつなげます。Skype for Business 管理センターを使用して、組織の自動応答を作成できます。

Skype for Business 管理センターで、新しい自動応答を作成するには、 [**通話ルーティング**]  >  [**自動応答**]、そして [**新規追加**]をクリックし、「[クラウドの自動応答を設定する](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant)」 の**手順 2** の指示に従って下さい。

**クラウドの自動応答の詳細については、 「[クラウドの自動応答を設定する](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)」を参照してください。**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 9: サービス用電話番号 (電話会議、通話キュー、自動応答) の割り当て

**上記の手順 4** で説明するサービス番号を取得したら、目的のサービスの各種類にサービス番号を割り当てる必要があります。たとえば、専用のサービス番号 (有料または無料) を使用する場合、その番号を会議ブリッジに割り当てる必要があります。

- 電話会議用に専用番号を会議用ブリッジに割り当てることができます。それには、[**Microsoft 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**電話会議**] の順に進み、会議ブリッジをクリックするか、「[電話会議ブリッジ上の有料・無料番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)」を参照してください。

- 自動応答については、**Microsoft 365 管理センター**  >  [**管理センター**]  >  [**Skype for Business**]  >  [**通話ルーティング**]  >  [**自動応答**] の順に移動して目的の自動応答をクリックすると、自動応答に専用番号を割り当てられます。[**一般**] ページでは、既に持っているサービス番号は [**電話番号**] ドロップ ダウンに表示されます。詳細については、「[クラウドの自動応答を設定する](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)」を参照してください。

- 通話キューについては、**Microsoft 365 管理センター**  >  [**管理センター**]  >  [**Skype for Business**]  >  [**通話ルーティング**]  >  [**通話キュー**] の順に移動して目的の通話キューをクリックすると、通話キューに専用番号を割り当てられます。[**一般**] ページでは、既に持っているサービス番号は [**電話番号**] ドロップ ダウンに表示されます。詳細については、「[クラウドの通話キューを作成する](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)」を参照してください。

**新しいサービス番号を取得し、既存のサービス番号を転送する方法の詳細については、 [サービスの電話番号の取得](/microsoftteams/getting-service-phone-numbers)  を参照してください。**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>手順 10: 組織のコミュニケーション クレジットをセットアップする

Skype for Business または Microsoft Teams で無料番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。通話プラン (国内または国際) と電話会議のユーザーのうち、**すべての発信先**にダイヤルアウトできるようにする必要があるユーザーについてもコミュニケーション クレジットを設定することをお勧めします。通話プランと電話会議のサブクリプションには多くの国や地域が含まれていますが、一部の発信先は含まれていない場合があります。コミュニケーション クレジットの請求に関する設定をせずに**コミュニケーション クレジット** ライセンスをユーザーに割り当ている状態で組織の持つ分数 (使用する国/地域の通話プランまたは電話会議プランにより異なります) が使い切られた場合、これらのユーザーは電話会議から発信またはダイヤルアウトできなくなります。推奨される入金額などの詳細情報については、「[コミュニケーション クレジットについて](what-are-communications-credits.md)」を参照してください。
  
> [!NOTE]
> 必要なコストを確認するには、[こちらで料金を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。

### <a name="to-set-up-communications-credits"></a>コミュニケーション クレジットをセットアップするには

1. 職場または学校のアカウントを使用して、Microsoft 365 にサインインします。

2. Office 365 管理ページ左側のナビゲーションで  **請求** > **サブスクリプション** > **アドオン** > **アドオンの購入** に進み、 **コミュニケーションクレジット** > **今すぐ購入** を選択してください。

3. [**コミュニケーション クレジット**] のサブクリプションのページで、ユーザーの情報を入力し [**次へ**] をクリックします。

4. 支払い情報を入力して、[**注文**] をクリックします。
    >[!IMPORTANT]
    >ボリューム ライセンスをお持ちのお客様は、支払い方法としてエンタープライズ契約番号を選択できます。エンタープライズ契約番号が複数ある場合は、支払いに使用するエンタープライズ契約番号を選択できます。(該当する場合は) エンタープライズ契約番号に関連付ける発注書番号を指定することもできます。
    
**コミュニケーションクレジットの設定に関する詳細については、 [組織のコミュニケーションクレジットを設定](set-up-communications-credits-for-your-organization.md) を参照してください。**
  
### <a name="assign-a-communications-credits-license-to-users"></a>コミュニケーション クレジットのライセンスをユーザーに割り当てる

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. Microsoft 365 管理センターの左側のナビゲーションで、[**ユーザー**]  >  [**アクティブなユーザー**] に進み、そのリストから一人、または複数のユーザーを選択します。

3. [操作] ウィンドウの [**製品ライセンス**] で [**編集**] をクリックします。

4. このライセンスを割り当てるには、[**製品ライセンス**] ページで [**コミュニケーション クレジット**] を [**オン**] に切り替え、[**保存**] をクリックします。

    > [!NOTE]
    > **Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、これを実行することをお勧めします。

**コミュニケーションクレジットのライセンスの割り当ての詳細については、 [組織用コミュニケーションクレジットの設定](set-up-communications-credits-for-your-organization.md) を参照してください。**

## <a name="related-topics"></a>関連トピック
[Office 365 の電話システムでできること](here-s-what-you-get-with-phone-system.md)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](/microsoftteams/getting-service-phone-numbers)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
