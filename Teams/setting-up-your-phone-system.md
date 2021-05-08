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
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
description: 組織のクラウド PBX (クラウド PBX) 電話システムを設定する方法について詳しく説明したステップ バイ ステップ ガイドMicrosoft 365または Office 365。
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701215"
---
# <a name="set-up-phone-system-in-your-organization"></a>組織内の電話システムの設定

次に示すのは、電話システム または Microsoft 365 を設定Office 365。 各手順の最後に、詳細な追加情報へのリンクを利用できます。

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>ステップ 1: 電話システムは、国または地域で利用可能なことを確認します。

1.    最初に [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) へ進み、ページの上部にある一覧表から国または地域を選択します。 
2.     **電話システム** での機能と詳細の一覧を確認します。 
3.    電話システムが使用可能な場合は、手順 2 に進みます。 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>手順 2: 電話システムおよび通話プランのライセンスを購入し、割り当てる

1 人のユーザー電話システム通話プラン ライセンスを割り当てる手順は、ユーザーまたは通話プランのライセンスを割り当てるMicrosoft 365同Office 365です。  複数のユーザーにライセンスを一括で割り当てて可能です。 詳細については、「アドオン ライセンスの[割り当Microsoft Teams」を参照してください](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

通話プランが国または地域で利用できない場合は、直接ルーティングを使用してオンプレミスのテレフォニー インフラストラクチャを接続して、電話システム。  詳細については、「[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)」を参照してください。

## <a name="step-3-get-phone-numbers-for-your-users"></a>ステップ 3: ユーザー向けの電話番号を取得する

組織内でユーザーを設定し、電話を掛けたり受けたりする前に、ユーザーの電話番号を取得する必要があります。

ユーザー用の番号を取得するには、次の 3 つの方法があります。
- 管理センターで新しい番号Teams取得します。
- 管理センターで使用できない新しいTeams取得します。
- 現在のサービス プロバイダーまたは携帯電話会社から、既存の番号をポートまたは転送して、Microsoft 365またはOffice 365。

これらの数値を表示、 **検索** 、取得、予約するには、[数値の追加] ページを使用する必要があります。 [ 国または地域]、[ 都道府県]、[ 市区町村] で検索してから、ユーザー用に必要となる電話番号の数を入力できます。

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>管理センターで新しいユーザーの電話番号Teams取得する

1. 職場または学校のアカウントを使用して、Microsoft 365 にサインインします。

2. [管理センター **] Teams移動します**。
    
3. 左側のナビゲーションで、[Voice電話 番号] に移動し、[追加]  >  **を** クリックし、画面の指示に従います。 
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>管理センターで使用できない新しいTeams取得する
  
(お客様の国/地域によっては) 管理センターで新しい番号を取得Teams場合があります。 この場合は、フォームをダウンロードして返送する必要があります。 新しいユーザー番号を要求する方法については、「組織の電話番号を [管理する」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>サービス プロバイダーまたは電話会社から電話番号を移行または転送する
  
- ユーザーに 999 以下の電話番号が必要な場合は、管理センターの[新しい電話番号のポート注文] ウィザードTeams使用できます。 「電話番号を電話番号に転送[する」の手順に従Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)電話番号を転送します。
    
- 999 を超える電話番号を移植する必要がある場合[](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)は、「組織の電話番号を管理して、ポート注文サービスの要求または注文を送信する」を参照してください。 

新しい電話番号を取得するか、既存の番号を転送する方法の詳細については、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 4: サービス用の電話番号 (電話会議、通話キュー、自動応答) を取得します。

Microsoft 365 または Office 365 からユーザーの電話番号を取得する以外に、電話会議 (会議ブリッジ用)、自動応答、通話キューなどのサービスの有料電話番号または無料電話番号を検索して取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。 たとえば、サービス番号は数百の呼び出しを同時に処理できるのに対し、ユーザーの電話番号は数件の通話のみを同時に処理できます。

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>管理センターで新しいサービス番号Teams取得する


1. 仕事用または学校用のアカウントでサインインします。

2. [管理センター **] Teams移動します**。

3. 左側のナビゲーション ウィンドウで、[Voice電話番号] に移動し、[新しいサービス番号]  >    >  **をクリックします**。

    > [!IMPORTANT]
    > Teams 管理センターの左側のナビゲーション ウィンドウに [音声] オプションを表示するには、まず、少なくとも 1 つの **Enterprise E5** ライセンス、1 つの **電話システム** アドオンライセンス、または 1 つの電話会議アドオン ライセンスを購入する必要があります。

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>管理センターで使用できない新しいTeams取得する
  
(お客様の国/地域によっては) 管理センターで新しい番号を取得Teams場合があります。 この場合は、フォームをダウンロードして返送する必要があります。 新しい番号を要求する方法については、「組織の電話番号を [管理する」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 

### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトに番号移行注文を手動で提出する必要があります。 承認状 (LOA) を使用して転送するサービス番号の種類 (有料と無料) ごとに個別のポート注文を送信する必要があります。 承認状（LOA)では、適切な種類のサービス番号を選択する必要があります。 Microsoft サポートに連絡する場合は、サービス番号 *(ユーザー* またはサブスクライバー番号ではなく) を転送するか、同時呼び出し容量で呼び出しボリュームを処理するのに十分ではない可能性があります。 電話番号を転送したり、自分の電話番号で他の操作をする場合は、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>手順 5: 通話プランを設定する場合

上記の手順に従っていれば、あなたはすでに電話システムとライセンス、通話プラン（手順２）を購入して割り当てられ、ユーザー用の電話番号を取得（手順３）したことになるので、あなたの通話プランは部分的に設定されています。
 通話プランを設定する手順を完了するには、「通話プランを設定 [する」を参照してください](set-up-calling-plans.md)。


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>手順 6: 電話会議を設定する場合

組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 Microsoft Teams、この状況だけの電話会議機能が含まれています。 モバイル デバイスまたは PC で Teams アプリを使用する代わりに、電話を使って会議にTeamsにコールインできます。
電話会議を設定する方法については、「電話会議をセットアップする」を参照[Teams。](set-up-audio-conferencing-in-teams.md)

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>手順 7: クラウドの通話キューを設定する場合

クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。

通話キューの詳細については、「クラウド呼び出しキュー [を作成する」を参照してください](create-a-phone-system-call-queue.md)。

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>手順 8: クラウドの自動応答を設定する場合

自動応答を使用すると、組織にコールインし、メニュー システムに移動して、適切な部署、通話キュー、ユーザー、またはオペレーターに移動できます。 組織の自動応答を作成するには、管理センターのTeams使用します。

クラウド自動応答の設定については、「クラウド自動応答を設定する」 [を参照してください](create-a-phone-system-auto-attendant.md)。


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 9: サービス用電話番号 (電話会議、通話キュー、自動応答) の割り当て

 **上記の手順 4** から、サービスの番号を作成したら、使用するサービスの種類ごとに番号を割り当てる必要があります。 たとえば、専用のサービス電話番号 (有料または無料) が必要な場合は、その番号を会議ブリッジに割り当てる必要があります。

- 電話会議の場合は、管理センターの会議ブリッジに移動して、Teamsに専用の番号を割り当て、画面の指示に  >    >  従います。  詳細については、「電話会議ブリッジの有料電話番号または無料電話番号を変更  [する」を参照してください](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

- 自動応答の場合は、管理センターの [音声自動応答] に移動し **、Teams** に従って、自動応答に専用の番号を  >    >  割り当てできます。  詳細については、「クラウド自動応答 [を設定する」を参照してください](create-a-phone-system-auto-attendant.md)。

- 通話キューの場合は、管理センターの音声通話キューに移動し、Teamsに従って、通話キューに専用の番号を割り  >    >  当てできます。 詳細については、「クラウド呼び出し [キューを作成する」を参照してください](create-a-phone-system-call-queue.md)。

新しいサービス番号を取得し、既存のサービス番号を転送する方法の詳細については、 [サービスの電話番号の取得](getting-service-phone-numbers.md)  を参照してください。

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>手順 10: 組織のコミュニケーション クレジットをセットアップする

無料電話番号を使用する場合は、Microsoft Teams通信クレジットを設定する必要があります。 Microsoft では、任意の宛先にダイヤルアウトする機能が必要な通話プラン (国内または国際) および電話会議ユーザー向け通信クレジットを設定する必要があります。 ご利用の通話プランまたは電話会議のサブスクリプションでは、多くの国や地域が含まれていますが、一部の発信先が含まれていない可能性があります。 

コミュニケーション クレジットの請求を設定しない場合や、ユーザーに **コミュニケーション クレジット** のライセンスを割り当てない場合に (国/地域の通話プランまたは電話会議プランに基づき) 組織の通話分数が不足すると、これらのユーザーは通話を発信することや、電話会議からダイヤルアウトすることができなくなります。 推奨される資金金額を含む詳細については、「通信[](what-are-communications-credits.md)クレジットとは」および「組織の通信クレジットを[設定する」を参照してください](set-up-communications-credits-for-your-organization.md)。
  

## <a name="related-topics"></a>関連トピック
[次に示すのは、電話システム または Microsoft 365 のOffice 365](here-s-what-you-get-with-phone-system.md)

[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
