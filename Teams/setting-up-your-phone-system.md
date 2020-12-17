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
description: Microsoft 365 または Office 365 で組織の電話システム (クラウド PBX) をセットアップする方法の詳細なステップ バイ ステップ ガイド。
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701215"
---
# <a name="set-up-phone-system-in-your-organization"></a>組織で電話システムをセットアップする

以下は、Microsoft 365 または Office 365 で電話システムをセットアップする手順ガイドです。その他の詳細情報へのリンクは、各手順の最後に表示されます。

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>ステップ 1: 電話システムは、国または地域で利用可能なことを確認します。

1.    最初に [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) へ進み、ページの上部にある一覧表から国または地域を選択します。 
2.     **電話システム** での機能と詳細の一覧を確認します。 
3.    電話システムが使用可能な場合は、手順 2 に進みます。 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>手順 2: 電話システムおよび通話プランのライセンスを購入し、割り当てる

電話システムと通話プランのライセンスを 1 人のユーザーに割り当てる手順は、Microsoft 365 または Office 365 ライセンスの割り当てと同じです。  複数のユーザーにライセンスを一括で割り当て込む方法も可能です。 詳細については、「Microsoft Teams アドオン ライセンスを割り当てる [」を参照してください](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

お客様の国または地域で通話プランを利用できない場合は、ダイレクト ルーティングを使用して、オンプレミスのテレフォニー インフラストラクチャを電話システムに接続します。  詳細については、「[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)」を参照してください。

## <a name="step-3-get-phone-numbers-for-your-users"></a>ステップ 3: ユーザー向けの電話番号を取得する

組織内でユーザーを設定し、電話を掛けたり受けたりする前に、ユーザーの電話番号を取得する必要があります。

ユーザー用の番号を取得するには、次の 3 つの方法があります。
- Teams 管理センターを使用して新しい番号を取得します。
- Teams 管理センターでは利用できない新しい番号を取得します。
- 現在のサービス プロバイダーまたは携帯電話会社から Microsoft 365 または Office 365 に既存の番号を移植または転送します。

これらの数値を表示、 **検索、取得** 、予約するには、[数値の追加] ページを使用する必要があります。 [ 国または地域]、[ 都道府県]、[ 市区町村] で検索してから、ユーザー用に必要となる電話番号の数を入力できます。

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>Teams 管理センターを使用して新しいユーザーの電話番号を取得する

1. 職場または学校のアカウントを使用して、Microsoft 365 にサインインします。

2. Teams 管理センター **に移動します**。
    
3. 左側のナビゲーションで [音声電話番号]**に** 移動し、[追加] をクリックして、画面  >  の指示に従います。 
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Teams 管理センターで利用できない新しい番号を取得する
  
(お客様の国/地域によって異なります) Teams 管理センターを使用して新しい番号を取得できない場合があります。 この場合は、フォームをダウンロードして返送する必要があります。 新しいユーザー番号を要求する方法については、「組織の電話番号を管理する [」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>サービス プロバイダーまたは電話会社から電話番号を移行または転送する
  
- ユーザーに必要な電話番号が 999 以下の場合は、Teams 管理センターで新しい電話番号のポート注文ウィザードを使用できます。 「電話番号を Teams に [転送する」](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) の手順に従って、電話番号を転送します。
    
- 999 を超える電話番号を移植する必要がある場合[](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)は、「組織の電話番号を管理してポート注文サービスの依頼または注文を送信する」を参照してください。 

新しい電話番号を取得するか、既存の番号を転送する方法の詳細については、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 4: サービス用の電話番号 (電話会議、通話キュー、自動応答) を取得します。

Microsoft 365 または Office 365 からユーザーの電話番号を取得できるだけでなく、電話会議 (会議ブリッジ用)、自動応答、通話キューなどのサービスの有料または無料電話番号を検索して取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。 たとえば、サービス番号は何百もの通話を同時に処理できるのに対し、ユーザーの電話番号は同時に数件の通話しか処理できません。

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>Teams 管理センターを使用して新しいサービス番号を取得する


1. 仕事用または学校用のアカウントでサインインします。

2. Teams 管理センター **に移動します**。

3. 左側のナビゲーション ウィンドウで、[音声 **電話番号]** に移動し、[新しい番号を追加] をクリックし、[新しい  >    >  **サービス番号] をクリックします**。

    > [!IMPORTANT]
    > Teams 管理センターの左側のナビゲーション ウィンドウに音声オプションを表示するには、まず、Enterprise **E5** ライセンス、電話システム アドオンライセンス、または電話会議アドオン ライセンスを1 つ以上購入する必要があります。

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Teams 管理センターで利用できない新しい番号を取得する
  
(お客様の国/地域によって異なります) Teams 管理センターを使用して新しい番号を取得できない場合があります。 この場合は、フォームをダウンロードして返送する必要があります。 新しい電話番号を要求する方法については、「組織の電話番号を管理する [」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 

### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトに番号移行注文を手動で提出する必要があります。 承認状 (LOA) を使用して移行するサービス番号の種類 (有料と無料電話番号) ごとに、個別の番号移行注文を送信する必要があります。 承認状（LOA)では、適切な種類のサービス番号を選択する必要があります。 Microsoft サポートに問い合わせするときに、サービス番号 *(ユーザー* またはサブスクライバー番号ではなく) を転送する場合、または同時呼び出しキャパシティーが通話ボリュームを処理するのに十分ではない可能性がある場合を指定します。 電話番号を転送したり、自分の電話番号で他の操作をする場合は、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>手順 5: 通話プランを設定する場合

上記の手順に従っていれば、あなたはすでに電話システムとライセンス、通話プラン（手順２）を購入して割り当てられ、ユーザー用の電話番号を取得（手順３）したことになるので、あなたの通話プランは部分的に設定されています。
 通話プランを設定する手順を完了するには、「通話プランを設定 [する」を参照してください](set-up-calling-plans.md)。


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>手順 6: 電話会議を設定する場合

組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 Microsoft Teams には、このような状況専用の電話会議機能が含まれています。 ユーザーは、モバイル デバイスや PC で Teams アプリを使用する代わりに、電話を使って Teams 会議にコールインできます。
電話会議の設定方法については、「Teams の電話会議をセットアップする」を [参照してください](set-up-audio-conferencing-in-teams.md)。

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>手順 7: クラウドの通話キューを設定する場合

クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。

通話キューの詳細については、「クラウド通話キューを作成 [する」を参照してください](create-a-phone-system-call-queue.md)。

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>手順 8: クラウドの自動応答を設定する場合

自動応答を使用すると、組織にコールインし、メニュー システムに移動して、適切な部署、通話キュー、ユーザー、またはオペレーターに移動できます。 Teams 管理センターを使用して、組織の自動応答を作成できます。

クラウド自動出席依頼の設定の詳細については、「クラウド自動応答を設定する」 [を参照してください](create-a-phone-system-auto-attendant.md)。


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 9: サービス用電話番号 (電話会議、通話キュー、自動応答) の割り当て

 **上記の手順 4** から、サービスの番号を作成したら、使用するサービスの種類ごとに番号を割り当てる必要があります。 たとえば、専用サービス電話番号 (有料または無料電話番号) が必要な場合は、その番号を会議ブリッジに割り当てる必要があります。

- 電話会議の場合 **、Teams** 管理センターの会議ブリッジに移動し、画面の指示に従って会議ブリッジに専用の番号を割り  >    >  当てできます。  詳細については、「電話会議  [ブリッジで有料](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)または無料電話番号を変更する」を参照してください。

- 自動応答の場合 **、Teams** 管理センターの音声自動応答に移動し、画面の指示に従って、自動応答に専用の番号を  >    >  割り当てできます。  詳細については、「クラウド自動応答 [を設定する」を参照してください](create-a-phone-system-auto-attendant.md)。

- 通話キューの場合は **、Teams** 管理センターの音声通話キューに移動し、画面の指示に従って、通話キューに専用の番号を  >    >  割り当てできます。 詳細については、「クラウド通話キュー [を作成する」を参照してください](create-a-phone-system-call-queue.md)。

新しいサービス番号を取得し、既存のサービス番号を転送する方法の詳細については、 [サービスの電話番号の取得](getting-service-phone-numbers.md)  を参照してください。

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>手順 10: 組織のコミュニケーション クレジットをセットアップする

Microsoft Teams で無料電話番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。 Microsoft では、任意の発信先にダイヤルアウトする機能が必要な通話プラン (国内または国際) および電話会議ユーザー用にコミュニケーション クレジットを設定する必要があります。 ご利用の通話プランまたは電話会議のサブスクリプションでは、多くの国や地域が含まれていますが、一部の発信先が含まれていない可能性があります。 

コミュニケーション クレジットの請求を設定しない場合や、ユーザーに **コミュニケーション クレジット** のライセンスを割り当てない場合に (国/地域の通話プランまたは電話会議プランに基づき) 組織の通話分数が不足すると、これらのユーザーは通話を発信することや、電話会議からダイヤルアウトすることができなくなります。 推奨される利用可能金額などの詳細については、「通信クレジットとは[](what-are-communications-credits.md)何か」および「組織の通信クレジット[を設定する」を参照してください](set-up-communications-credits-for-your-organization.md)。
  

## <a name="related-topics"></a>関連項目
[Microsoft 365 または Office 365 の電話システムで利用Office説明します。](here-s-what-you-get-with-phone-system.md)

[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
