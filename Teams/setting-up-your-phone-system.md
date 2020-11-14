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
description: Microsoft 365 または Office 365 で組織の電話システム (クラウド PBX) を設定する方法について詳しく説明しているステップバイステップガイドです。
ms.openlocfilehash: 14a2fa971d32aeb7c0dca8200a72ad4895be4d44
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031383"
---
# <a name="set-up-phone-system-in-your-organization"></a>組織で電話システムをセットアップする

Microsoft 365 または Office 365 で電話システムをセットアップするためのステップバイステップガイドを次に示します。詳細情報へのリンクについては、各手順の最後に記載されています。

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>ステップ 1: 電話システムは、国または地域で利用可能なことを確認します。

1.    最初に [オーディオ会議や通話プランのための国および地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) へ進み、ページの上部にある一覧表から国または地域を選択します。 
2.     **電話システム** での機能と詳細の一覧を確認します。 
3.    電話システムが使用可能な場合は、手順 2 に進みます。 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>手順 2: 電話システムおよび通話プランのライセンスを購入し、割り当てる

電話システムと通話プランのライセンスを1人のユーザーに割り当てるには、手順は Microsoft 365 または Office 365 ライセンスの割り当てと同じです。  複数のユーザーに一括してライセンスを割り当てることもできます。 詳細については、「 [Microsoft Teams のアドオンライセンスを割り当てる](teams-add-on-licensing/assign-teams-add-on-licenses.md)」を参照してください。

お住まいの国または地域で通話プランを利用できない場合は、ダイレクトルーティングを使用してオンプレミスのテレフォニーインフラストラクチャを電話システムに接続することを検討してください。  詳細については、「[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)」を参照してください。

## <a name="step-3-get-phone-numbers-for-your-users"></a>ステップ 3: ユーザー向けの電話番号を取得する

組織内でユーザーを設定し、電話を掛けたり受けたりする前に、ユーザーの電話番号を取得する必要があります。

ユーザー用の番号を取得するには、次の 3 つの方法があります。
- Teams 管理センターを使用して、新しい番号を取得します。
- Teams 管理センターで利用できない新しい番号を取得します。
- 現在のサービスプロバイダーまたは電話会社から、Microsoft 365 または Office 365 に既存の番号を移行するか、または転送します。

[ **番号の追加** ] ページを使用して、これらの番号の表示、検索、取得、および予約を行う必要があります。 [ 国または地域]、[ 都道府県]、[ 市区町村] で検索してから、ユーザー用に必要となる電話番号の数を入力できます。

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>Teams 管理センターを使用して新しいユーザーの電話番号を取得する

1. 職場または学校のアカウントを使用して、Microsoft 365 にサインインします。

2. **Teams 管理センター** に移動します。
    
3. 左のナビゲーションで、[ **音声**  >  **電話番号** ] に移動し、[ **追加** ] をクリックして、画面の指示に従います。
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Teams 管理センターで利用できない新しい番号を取得する
  
場合によっては (お住まいの国/地域によっては)、Teams 管理センターを使用して新しい電話番号を取得することはできません。 この場合、フォームをダウンロードして、もう一度送信する必要があります。 新しいユーザー番号を要求する方法については、「 [組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」を参照してください。   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>サービス プロバイダーまたは電話会社から電話番号を移行または転送する
  
- ユーザーの電話番号を999以上にする必要がある場合は、Teams 管理センターの新しい電話番号の **ポート注文** ウィザードを使用できます。 「電話 [番号をチームに転送](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) して電話番号を転送する」の手順に従います。
    
- 999を超える電話番号を移植する必要がある場合は、「 [組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) して、ポート注文サービスの依頼または注文を送信する」を参照してください。 

新しい電話番号を取得するか、既存の番号を転送する方法の詳細については、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 4: サービス用の電話番号 (電話会議、通話キュー、自動応答) を取得します。

Microsoft 365 または Office 365 からユーザーの電話番号を取得することに加えて、電話会議 (会議ブリッジ用)、自動応答、通話キューなどのサービスの有料または無料の電話番号を検索して取得することができます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。 たとえば、サービス番号では何百もの通話を同時に処理できますが、ユーザーの電話番号は同時に複数の通話を処理できます。

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>Teams 管理センターを使用して新しいサービス番号を取得する


1. 職場または学校のアカウントを使用してサインインします。

2. **Teams 管理センター** に移動します。

3. 左側のナビゲーションウィンドウで、[電話番号を追加 **する]** に移動し  >  **Phone numbers**  >  **Add new number** 、[ **新しいサービス番号** ] をクリックします。

    > [!IMPORTANT]
    > チーム管理センターの左側のナビゲーションウィンドウで [ **音声** ] オプションを表示するには、最初に少なくとも1つの **Enterprise E5 ライセンス** 、1つの **電話システム** アドオンライセンス、または1つの電話 **会議** アドオンライセンスを購入する必要があります。

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Teams 管理センターで利用できない新しい番号を取得する
  
場合によっては (お住まいの国/地域によっては)、Teams 管理センターを使用して新しい電話番号を取得することはできません。 この場合、フォームをダウンロードして、もう一度送信する必要があります。 新しい番号を要求する方法については、「 [組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」を参照してください。 

### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトに番号移行注文を手動で提出する必要があります。 各種のサービス番号 (有料と無料) ごとに個別のポート注文を送信する必要があります。これは、承認状 (LOA) を使用して転送されます。 承認状（LOA)では、適切な種類のサービス番号を選択する必要があります。 Microsoft サポートに問い合わせるときは、サービス番号を転送する ( *ユーザーまたは加入者番号* ではなく) ことを指定します。または、同時通話容量が通話ボリュームを処理するには十分でない可能性があります。 電話番号を転送したり、自分の電話番号で他の操作をする場合は、 [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>手順 5: 通話プランを設定する場合

上記の手順に従っていれば、あなたはすでに電話システムとライセンス、通話プラン（手順２）を購入して割り当てられ、ユーザー用の電話番号を取得（手順３）したことになるので、あなたの通話プランは部分的に設定されています。
 通話プランの設定手順については、「 [通話プランをセットアップ](set-up-calling-plans.md)する」をご覧ください。


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>手順 6: 電話会議を設定する場合

組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 Microsoft Teams には、このような状況での電話会議機能が含まれています。 ユーザーは、モバイルデバイスや PC で Teams アプリを使う代わりに、電話を使って Teams 会議にコールインすることができます。
電話会議をセットアップする方法については、「 [Teams の電話会議](set-up-audio-conferencing-in-teams.md)をセットアップする」を参照してください。

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>手順 7: クラウドの通話キューを設定する場合

クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。

通話キューの詳細については、「 [クラウド通話キューを作成する](create-a-phone-system-call-queue.md)」を参照してください。

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>手順 8: クラウドの自動応答を設定する場合

自動応答は、組織にコールインしているユーザーに対して、適切な部署、通話キュー、人、またはオペレーターにアクセスするためのメニューシステムの操作を許可します。 Teams 管理センターを使用して、組織の自動応答を作成できます。

クラウド自動応答のセットアップについては、「 [クラウド自動応答をセットアップする](create-a-phone-system-auto-attendant.md)attendendant を参照してください。


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>手順 9: サービス用電話番号 (電話会議、通話キュー、自動応答) の割り当て

 **上記の手順 4** から、サービスの番号を作成したら、使用するサービスの種類ごとに番号を割り当てる必要があります。 たとえば、専用のサービス電話番号 (有料またはフリーダイヤル) が必要な場合は、電話会議ブリッジに電話番号を割り当てる必要があります。

- 電話会議の場合は、 **Teams 管理センター** の会議ブリッジにアクセスし、指示に従って、会議ブリッジに専用の電話番号を割り当てることができ  >  **Meetings**  >  **Conference bridges** ます。  詳細については、「  [電話会議ブリッジの有料または](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)無料の電話番号を変更する」を参照してください。

- 自動応答の場合は、 **Teams 管理センター** の  >  **音声**  >  **自動応答** にアクセスし、画面の指示に従って、自動応答に専用の番号を割り当てることができます。  詳細については、「 [クラウド自動応答をセットアップする](create-a-phone-system-auto-attendant.md)」を参照してください。

- 通話キューの場合は、 **Teams 管理センター** の  >  **音声**  >  **通話キュー** に移動して、画面の指示に従って専用の番号を通話キューに割り当てることができます。 詳細については、「 [クラウド通話キューを作成する](create-a-phone-system-call-queue.md)」を参照してください。

新しいサービス番号を取得し、既存のサービス番号を転送する方法の詳細については、 [サービスの電話番号の取得](getting-service-phone-numbers.md)  を参照してください。

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>手順 10: 組織のコミュニケーション クレジットをセットアップする

Microsoft Teams で無料電話番号を使用する場合は、通信クレジットを設定する必要があります。 Microsoft は、通話プラン (国内または国際電話) と、発信先にダイヤルアウトする機能が必要な電話会議ユーザーに対して、通信クレジットを設定することをお勧めします。 ご利用の通話プランまたは電話会議のサブスクリプションでは、多くの国や地域が含まれていますが、一部の発信先が含まれていない可能性があります。 

コミュニケーション クレジットの請求を設定しない場合や、ユーザーに **コミュニケーション クレジット** のライセンスを割り当てない場合に (国/地域の通話プランまたは電話会議プランに基づき) 組織の通話分数が不足すると、これらのユーザーは通話を発信することや、電話会議からダイヤルアウトすることができなくなります。 推奨資金調達金額などの詳細については、「 [通信クレジットとは](what-are-communications-credits.md) 」を参照してください。また、 [組織の通信クレジットを設定](set-up-communications-credits-for-your-organization.md)します。
  

## <a name="related-topics"></a>関連項目
[Microsoft 365 または Office 365 の電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Skype for Business および Microsoft Teams のサービス電話番号の取得](getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
