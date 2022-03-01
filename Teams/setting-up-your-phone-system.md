---
title: 組織内の電話システムの設定
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
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
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: 詳細な手順については、組織内の組織のTeams 電話システムを設定する方法を説明Microsoft 365。
ms.openlocfilehash: 1a8f7ed554a360b94e568058be29697c0f2b1767
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039985"
---
# <a name="set-up-phone-system-in-your-organization"></a>組織内の電話システムの設定

この記事では、電話システム クラウドで通話制御とプライベート ブランチ Exchange (PBX) 機能を有効にするための 電話システム-Microsoft のテクノロジ Microsoft 365を設定するためのコンテンツのロードマップを示します。 詳細な情報へのリンクは、各手順の最後に表示されます。 

この記事を読む前に、「What [is 電話システム](what-is-phone-system-in-office-365.md) and [Here's](here-s-what-you-get-with-phone-system.md) get what you get with 電話システム. 後者の 2 つの記事では、電話システム要件と機能について説明します。    

この記事では、次の手順について説明します。 

- [手順 1: ライセンスを購入して割り当電話システムする](#step-1-buy-and-assign-a-phone-system-license)  
- [手順 2: PSTN 接続オプションを選択する](#step-2-choose-a-pstn-connectivity-option) 
- [ステップ 3: ユーザー向けの電話番号を取得する](#step-3-get-phone-numbers-for-your-users)
- [手順 4: サービスの電話番号を取得する](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [手順 5: 通話キューを設定する場合](#step-5-if-you-want-to-set-up-a-call-queue) 
- [手順 6: 自動応答を設定する場合](#step-6-if-you-want-to-set-up-an-auto-attendant) 
- [手順 7: 無料電話番号のコミュニケーション クレジットを設定する](#step-7-set-up-communications-credits-for-toll-free-numbers)
 

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>手順 1: ライセンスを購入して割り当電話システムする

1 人の電話システムユーザーにライセンスを割り当てる手順は、ライセンスの割り当てとMicrosoft 365です。 複数のユーザーにライセンスを一括で割り当てて可能です。 使用可能な 電話システム ライセンスとライセンスの取得と割り当て方法の詳細については、「Teams [](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md) アドオン ライセンス」および「Microsoft Teams アドオン ライセンスの割り当て」を参照[してください](/teams-add-on-licensing/assign-teams-add-on-licenses.md)。

## <a name="step-2-choose-a-pstn-connectivity-option"></a>手順 2. PSTN 接続オプションを選択する 
 
ユーザーが外部通話を発信および受信するには、PSTN (公衆交換電話網電話システム接続する必要があります。 Microsoft では、PSTN に接続するための次のオプションを複数提供しています。 

- 通話プラン。 MICROSOFT を PSTN 通信事業者として使用する、クラウド内のすべてソリューション。 

- 演算子Connect。 既存の運送業者が Microsoft Operator Connect プログラムに参加している場合は、PSTN 通話とセッション ボーダー コントローラー (SBC) を管理できます。 

- ダイレクト ルーティング。 SPC を接続して、独自の PSTN 通信業者を使用電話システム。 

すべての接続オプションの詳細については、「 [PSTN 接続オプション」を参照してください](pstn-connectivity.md)。   

## <a name="step-3-get-phone-numbers-for-your-users"></a>ステップ 3: ユーザー向けの電話番号を取得する

組織内でユーザーを設定し、電話を掛けたり受けたりする前に、ユーザーの電話番号を取得する必要があります。

ユーザーの電話番号を管理する方法については、次の記事を参照してください。 ユーザーの番号を管理する方法は、選択した PSTN 接続オプションによって異なります。   

- [組織の電話番号を管理する](manage-phone-numbers-landing-page.md) - PSTN 接続オプションに応じて番号を取得および管理するための特定の記事へのリンクを含む、電話番号の種類の概要を示します。 2 種類のユーザー電話番号 [について説明します](manage-phone-numbers-landing-page.md#user-telephone-numbers)。 
 
- [ユーザーの電話番号を割り当て](assign-change-or-remove-a-phone-number-for-a-user.md) 、変更、または削除する - 取得した電話番号を割り当て、管理する方法について説明します。 
 
- [取得できる電話番号](how-many-phone-numbers-can-you-get.md) の数 – 購入して割り当てた電話番号の種類とライセンスの種類に応じて、取得できる電話番号の数について説明します。 


## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>手順 4: サービス (通話キュー、自動応答) の電話番号を取得する

ユーザーの電話番号を取得する以外に、自動応答や通話キューなどのサービスの有料電話番号または無料電話番号を取得できます。 サービス番号は何百もの呼び出しを同時に処理できるのに対し、ユーザーの電話番号は数件の通話のみを同時に処理できます。   

ライセンスに含まれる Microsoft からサービス番号を取得できます。 オペレーターサービスまたは直接ルーティングを通じて PSTN Connect接続している場合は、独自の通信事業者またはオペレーターが提供するサービス番号を使用できます。 

詳細については、次を参照してください:

- [組織の電話番号を管理する](manage-phone-numbers-landing-page.md) - PSTN 接続オプションに応じて番号を取得および管理するための特定の記事へのリンクを含む、電話番号の種類の概要を示します。  
ライセンスに [含まれる](manage-phone-numbers-landing-page.md#service-telephone-numbers) Microsoft から利用できるサービス電話番号について説明します。 オペレーターサービスまたはダイレクト ルーティングによって提供されるサービスConnectについては、プロバイダーにお問い合わせください。 

- [取得できる電話番号](how-many-phone-numbers-can-you-get.md) の数 – 購入して割り当てた電話番号の種類とライセンスの種類に応じて、取得できる電話番号の数について説明します。 

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>手順 5: 通話キューを設定する場合

通話キューには、他のユーザーが組織の電話番号にコールインするときに使用される応答メッセージ、通話を自動的に保留にする機能、通話を処理する次に利用可能な通話エージェントを検索する機能が含まれます。 組織では単一または複数の通話キューを作成できます。 

通話キューの詳細については、「通話キューを作成 [する」を参照してください](create-a-phone-system-call-queue.md)。

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>手順 6: 自動応答を設定する場合

自動応答を使用すると、組織にコールインするユーザーがメニュー システム内を移動して、適切な部署、通話キュー、ユーザー、またはオペレーターにアクセスできます。  

自動応答の設定については、「自動応答を設定 [する」を参照してください](create-a-phone-system-auto-attendant.md)。

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>手順 7: 無料電話番号のコミュニケーション クレジットを設定する

無料電話番号を使用する場合は、Microsoft Teams 通信クレジットを設定する必要があります。 無料電話の通話は、分単位で請求され、コミュニケーション クレジットの残高がプラスである必要があります。 

コミュニケーション クレジットは、次のようにフリーダイヤルの電話番号を追加する便利な方法です。 

- 自動応答や通話キューなどの音声アプリのサービス番号。 

- 国内通話プランのサブスクリプションがある場合、または国内通話プランと国際通話プランのサブスクリプションに含まれる番号を超えている場合に、国際電話番号をダイヤルします。 

- 毎月の分単位を使い果たしたら、1 分あたりのダイヤルアウトと支払いを行います。 

詳細については、「通信クレジット [とは」および](what-are-communications-credits.md) 「組織の通信クレジット [を設定する」を参照してください](set-up-communications-credits-for-your-organization.md)。
  

## <a name="related-topics"></a>関連項目

- [電話システムとは](what-is-phone-system-in-office-365.md)

- [電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

- [組織の電話番号を管理する](manage-phone-numbers-landing-page.md)


    
  
 
