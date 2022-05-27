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
description: Microsoft 365で組織のTeams 電話システムを設定する方法を詳しく説明するステップ バイ ステップ ガイド。
ms.openlocfilehash: 12e202fed6ad63835c364662194be2eabf872b31
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681928"
---
# <a name="set-up-phone-system-in-your-organization"></a>組織内の電話システムの設定

この記事では、電話システムを設定するためのコンテンツのロードマップを示します。-Microsoft 365 クラウドで通話制御と Private Branch Exchange (PBX) 機能を有効にする Microsoft のテクノロジ。 詳細な情報へのリンクは、各手順の最後で入手できます。

この記事を読む前に、「[電話システムとは何](what-is-phone-system-in-office-365.md)か」を読み、電話システム[で得られる内容を確認](here-s-what-you-get-with-phone-system.md)してください。 後者の 2 つの記事では、電話システム要件と機能について説明します。

この記事では、次の手順について説明します。

- [手順 1: 電話システム ライセンスを購入して割り当てる](#step-1-buy-and-assign-a-phone-system-license)
- [手順 2: PSTN 接続オプションを選択する](#step-2-choose-a-pstn-connectivity-option)
- [ステップ 3: ユーザー向けの電話番号を取得する](#step-3-get-phone-numbers-for-your-users)
- [手順 4: サービスの電話番号を取得する](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [手順 5: 通話キューを設定する場合](#step-5-if-you-want-to-set-up-a-call-queue)
- [手順 6: 自動応答を設定する場合](#step-6-if-you-want-to-set-up-an-auto-attendant)
- [手順 7: フリーダイヤル番号の通信クレジットを設定する](#step-7-set-up-communications-credits-for-toll-free-numbers)

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>手順 1: 電話システム ライセンスを購入して割り当てる

電話システム ライセンスを 1 人のユーザーに割り当てるには、Microsoft 365 ライセンスの割り当てと同じ手順を実行します。 ライセンスを複数のユーザーに一括で割り当てることもできます。 使用可能な電話システム ライセンスとライセンスの取得と割り当て方法の詳細については、「[アドオン ライセンスのTeams](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing)とアドオン ライセンス[Microsoft Teams割り当てる](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)」を参照してください。

## <a name="step-2-choose-a-pstn-connectivity-option"></a>手順 2. PSTN 接続オプションを選択する

ユーザーが外部通話を発信および受信できるようにするには、電話システムを公衆交換電話網 (PSTN) に接続する必要があります。 Microsoft には、PSTN に接続するための次のような複数のオプションが用意されています。

- プランの呼び出し。 MICROSOFT を PSTN 通信事業者として使用する、クラウド内のオール イン ソリューション。

- オペレーター接続。 既存の通信事業者が Microsoft オペレーター接続 プログラムに参加している場合は、PSTN 通話とセッション ボーダー コントローラー (SBC) を管理できます。

- ダイレクト ルーティング。 SBC を電話システムに接続して、独自の PSTN 通信事業者を使用します。

すべての接続オプションの詳細については、「 [PSTN 接続オプション](pstn-connectivity.md)」を参照してください。

## <a name="step-3-get-phone-numbers-for-your-users"></a>ステップ 3: ユーザー向けの電話番号を取得する

組織内でユーザーを設定し、電話を掛けたり受けたりする前に、ユーザーの電話番号を取得する必要があります。

ユーザーの電話番号を管理する方法については、次の記事を参照してください。 ユーザーの番号を管理する方法は、選択した PSTN 接続オプションによって異なります。

- [組織の電話番号を管理](manage-phone-numbers-landing-page.md) する - PSTN 接続オプションに応じて番号を取得および管理するための特定の記事へのリンクを含む電話番号の種類の概要を示します。
2 種類の [ユーザー電話番号](manage-phone-numbers-landing-page.md#user-telephone-numbers)について説明します。

- [ユーザーの電話番号の割り当て、変更、または削除](assign-change-or-remove-a-phone-number-for-a-user.md) – 取得した電話番号を割り当て、管理する方法について説明します。

- 電話番号[を取得できる電話番号の数](how-many-phone-numbers-can-you-get.md) – 電話番号の種類と、購入して割り当てたライセンスの種類に応じて取得できる電話番号の数について説明します。

## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>手順 4: サービスの電話番号を取得する (通話キュー、自動応答)

ユーザーの電話番号を取得するだけでなく、自動応答や通話キューなどのサービスの有料電話番号またはフリーダイヤル電話番号を取得することもできます。 サービス番号は数百の呼び出しを同時に処理できますが、ユーザーの電話番号は同時にいくつかの通話のみを処理できます。

ライセンスに含まれる Microsoft からサービス番号を取得できます。 オペレーター接続またはダイレクト ルーティングを介した PSTN 接続がある場合は、独自の通信事業者またはオペレーターによって提供されるサービス番号を使用できます。

詳細については、次を参照してください:

- [組織の電話番号を管理](manage-phone-numbers-landing-page.md) する - PSTN 接続オプションに応じて番号を取得および管理するための特定の記事へのリンクを含む電話番号の種類の概要を示します。
ライセンスに含まれる Microsoft から入手できる [サービス電話番号](manage-phone-numbers-landing-page.md#service-telephone-numbers) について説明します。 オペレーター接続またはダイレクト ルーティングによって提供されるサービス番号については、プロバイダーにお問い合わせください。

- 電話番号[を取得できる電話番号の数](how-many-phone-numbers-can-you-get.md) – 電話番号の種類と、購入して割り当てたライセンスの種類に応じて取得できる電話番号の数について説明します。

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>手順 5: 通話キューを設定する場合

通話キューには、他のユーザーが組織の電話番号を呼び出すときに使用されるあいさつ、通話を自動的に保留にする機能、通話を処理するために次に使用可能な通話エージェントを検索する機能が含まれます。 組織では単一または複数の通話キューを作成できます。

呼び出しキューの詳細については、「呼び出 [しキューの作成](create-a-phone-system-call-queue.md)」を参照してください。

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>手順 6: 自動応答を設定する場合

自動応答を使用すると、組織に呼び出すユーザーがメニュー システムを移動して、適切な部署に移動したり、キュー、ユーザー、またはオペレーターを呼び出したりできます。

自動応答の設定の詳細については、「自動応答 [を設定する」を](create-a-phone-system-auto-attendant.md)参照してください。

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>手順 7: フリーダイヤル番号の通信クレジットを設定する

Microsoft Teamsでフリーダイヤル番号を使用する場合は、通信クレジットを設定する必要があります。 無料電話の通話は、分単位で請求され、コミュニケーション クレジットの残高がプラスである必要があります。

通信クレジットは、次のように使用するフリーダイヤル番号を追加する便利な方法です。

- 自動応答や通話キューなど、音声アプリのサービス番号を使用します。

- 国内通話プランのサブスクリプションがある場合、または国内通話プランと国際通話プランサブスクリプションに含まれる電話番号を超えて国際電話番号にダイヤルする場合。

- 毎月の分割り当てがなくなると、ダイヤルアウトして 1 分あたりの支払いを行います。

詳細については、「 [コミュニケーション クレジットとは」](what-are-communications-credits.md) と「 [組織の通信クレジットの設定」を参照してください](set-up-communications-credits-for-your-organization.md)。

## <a name="related-topics"></a>関連項目

- [電話システムとは](what-is-phone-system-in-office-365.md)

- [電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

- [組織の電話番号を管理する](manage-phone-numbers-landing-page.md)
