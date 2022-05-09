---
title: オペレーター接続会議の計画
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 10/28/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: オペレーター接続会議の詳細 (要件やデプロイの計画など) について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d910fd9d464d1c4ff452da70a3bde039e4748123
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257540"
---
# <a name="plan-for-operator-connect-conferencing"></a>オペレーター接続会議の計画

Microsoft 電話会議では、公衆交換電話網 (PSTN) の電話番号を使用して、会議にダイヤルインし、会議からダイヤルアウトする機能を提供します。  参加者は、音声専用の会議ブリッジを使用してMicrosoft Teams会議に参加します。

オペレーター接続会議機能を使用すると、組織はサードパーティのオペレーターの電話番号を使用してMicrosoft Teams会議に参加できます。 現在のオペレーターが Microsoft オペレーター接続 プログラムの一部である場合は、オペレーターから電話会議ブリッジに電話番号を追加し、それを使用して会議に参加できます。

オペレーター接続会議機能がないと、組織は Microsoft から提供された電話番号のみを電話会議ブリッジに使用できます。

>[!NOTE]
>Microsoft オペレーター接続 プログラムの一部である電話番号プロバイダーは、この記事で "オペレーター" として参照されています。
>
>オペレーターが Microsoft オペレーター接続 プログラムに参加しているかどうかを確認するには、[Microsoft 365 オペレーター接続 ディレクトリ](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)を参照してください。

この記事では、オペレーター接続会議について説明します。

- [利点](#benefits)
- [ライセンス要件と課金](#licensing-requirements-and-billing)
- [Microsoft 電話会議に関する追加情報](#additional-information-on-microsoft-audio-conferencing)

オペレーター接続会議の構成の詳細については、「[オペレーター接続会議の構成」を](operator-connect-conferencing-configure.md)参照してください。

組織の一部のユーザーが PSTN 電話番号に対して外部通話を行う必要がある場合は、引き続き通話プランが必要です。 外部 PSTN 接続にサード パーティ製オペレーターを使用する方法については、「[オペレーター接続の計画」を](operator-connect-plan.md)参照してください。

## <a name="benefits"></a>利点

オペレーター接続会議には、次の利点があります。

- **オペレーターと Microsoft 間の電話番号の柔軟な割り当て。** Microsoft とオペレーターの両方の電話番号 (Microsoft 電話会議標準サブスクリプションのみ) を使用するか、オペレーターからの電話番号のみを使用します (オペレーター接続会議 ライセンスのみ)。

- **オペレーターが管理するインフラストラクチャ。** オペレーターは、セッション ボーダー コントローラー (SBC) と Microsoft との相互接続性を管理し、追加のハードウェア購入と管理から節約できます。

- **デプロイを高速化し、簡単に行います。** オペレーターにすばやく接続し、Teams管理センターから電話会議ブリッジに電話番号を割り当てます。

- **サポートと信頼性の強化。** オペレーターは、サービス サポートを向上させるためのテクニカル サポートと共有サービス レベル アグリーメントを提供し、Azure を利用した直接ピアリングによって、信頼性を高めるために 1 対 1 のネットワーク接続を作成します。

次の場合は、オペレーター接続会議が組織に適したソリューションである可能性があります。

- 既存の電話番号プロバイダーとの **契約を維持** する必要がある

- 既存の Microsoft 電話会議ブリッジの **グローバル カバレッジを拡大** する

- 新しい電話番号プロバイダーから **電話会議の電話番号をソース** にする

- **Microsoft 電話会議は、お客様の地理的な場所では利用できません**

- 無料電話番号の使用や、サブスクリプションに含まれていない国の電話番号へのTeams会議からの発信通話など、分単位の有料モデルを使用して **電話会議サービスのオペレーターを活用** する必要がある

## <a name="licensing-requirements-and-billing"></a>ライセンス要件と課金

組織する会議に参加するためにオペレーター接続会議番号が必要なユーザーには、Microsoft 電話会議標準サブスクリプションまたは Microsoft オペレーター接続会議 ライセンスが割り当てられている必要があります。

### <a name="audio-conferencing-standard-subscription"></a>電話会議 Standard サブスクリプション

Microsoft 電話会議 Standard サブスクリプションは、Microsoft Teams ライセンスのアドオンとして購入でき、Microsoft 365 E5およびOffice 365 E5サブスクリプションにも含まれます。

電話会議標準サブスクリプションを使用すると、サブスクライバーは Microsoft の電話番号を使用し、オペレーターからの番号を使用して電話会議ブリッジを拡張できます。 サブスクライバーは、microsoft 経由でルーティングするTeams会議からの送信呼び出しと、オペレーターを介してルーティングする呼び出しを決定することもできます。

詳細については、「[**オペレーター接続会議の構成」を**](operator-connect-conferencing-configure.md)参照してください。

### <a name="operator-connect-conferencing-license"></a>オペレーター接続会議 ライセンス

Microsoft オペレーター接続会議 ライセンスは、Microsoft Teams ライセンスのアドオンとして取得できます。

オペレーター接続会議 ライセンスを使用すると、サブスクライバーはオペレーターの電話番号を使用できますが、Microsoft からの電話番号は含まれません。 Teams会議からのすべての発信通話は、オペレーターを介してルーティングする必要があります。

詳細については、「[**オペレーター接続会議の構成」を**](operator-connect-conferencing-configure.md)参照してください。

>[!Note]
>会議参加者は、オペレーター接続会議機能を備えたユーザーが開催する会議に参加するために、電話会議標準サブスクリプション ライセンスまたはオペレーター接続会議 ライセンスを必要としません。

オペレーター接続会議では、Microsoft は、組織で使用される電話会議ライセンスの種類、Microsoft 電話会議またはオペレーター接続会議、および Microsoft から提供された電話番号の使用に応じて組織に請求します。

オペレーターは、提供されたオペレーター接続会議番号の使用に対して組織に請求します。

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Microsoft 電話会議に関する追加情報

Microsoft 電話会議を使用すると、参加者は PSTN 電話番号でダイヤルインするか、PSTN 電話番号にダイヤルアウトして、Microsoft Teams会議に参加できます。 組織で使用できる Microsoft 電話会議機能の詳細については、「[Microsoft 365の電話会議](audio-conferencing-in-office-365.md)」を参照してください。
