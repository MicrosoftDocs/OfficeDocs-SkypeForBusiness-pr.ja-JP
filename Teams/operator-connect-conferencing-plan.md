---
title: オペレーター会議のConnect計画
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
description: オペレーター と会議のConnect要件や展開の計画などについて説明します。
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
# <a name="plan-for-operator-connect-conferencing"></a>オペレーター会議のConnect計画

Microsoft 電話会議では、公衆交換電話網 (PSTN) の電話番号を使用して電話会議にダイヤルインし、会議からダイヤルアウトすることができます。  参加者はMicrosoft Teams会議ブリッジを使用して会議に参加します。

オペレーター Connect会議機能を使用すると、組織はサード パーティのオペレーターの電話番号を使用して、会議にMicrosoft Teamsできます。 現在のオペレーターが Microsoft Operator Connect プログラムの一部である場合は、オペレーターから電話会議ブリッジに電話番号を追加し、それらを使用して会議に参加できます。

オペレーターがConnect機能を使用しない場合、組織は電話会議ブリッジに Microsoft が提供する電話番号のみを使用できます。

>[!NOTE]
>Microsoft Operator Connect プログラムの一部である電話番号プロバイダーは、この記事で "オペレーター" として参照されています。
>
>オペレーターが Microsoft Operator Connect プログラムに参加Microsoft 365については、 Connect[してください](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。

この記事では、オペレーターと会議Connect説明します。

- [利点](#benefits)
- [ライセンス要件と課金](#licensing-requirements-and-billing)
- [Microsoft 電話会議に関する追加情報](#additional-information-on-microsoft-audio-conferencing)

オペレーター会議の構成については、「オペレーターと会議Connect構成[する」をConnectしてください](operator-connect-conferencing-configure.md)。

組織の一部のユーザーが PSTN 電話番号への外部通話を行う必要がある場合でも、通話プランが必要です。 外部 PSTN 接続にサード パーティのオペレーターを使用する方法については、「Plan for Operator Connect 」を[参照してください](operator-connect-plan.md)。

## <a name="benefits"></a>利点

オペレーター Connect会議には、次の利点があります。

- **オペレーターと Microsoft の間の電話番号の柔軟な割り当て。** Microsoft とオペレーターの両方の電話番号 (Microsoft 電話会議 Standard サブスクリプションのみ) を使用するか、オペレーターの電話番号のみを使用します (オペレーター Connect 会議ライセンスのみ)。

- **オペレーターが管理するインフラストラクチャ。**  オペレーターがセッション ボーダー コントローラー (SBC) と Microsoft との相互接続を管理し、追加のハードウェアの購入と管理からユーザーを節約します。

- **デプロイの高速化、簡単。**  オペレーターにすばやく接続し、管理センターから電話会議ブリッジに電話番号Teamsします。

- **サポートと信頼性の強化。**  オペレーターは、サービス サポートを向上させるためにテクニカル サポートと共有サービス レベル アグリーメントを提供します。また、Azure を利用した直接ピアリングでは、信頼性を向上させるために 1 対 1 のネットワーク接続が作成されます。

オペレーター Connect会議は、次の場合に組織に最適なソリューションである可能性があります。

- 既存の **電話番号プロバイダーとの** 契約を維持する

- 既存の Microsoft 電話会議 **ブリッジのグローバル** な対象範囲を拡大する場合

- 新しい **電話番号プロバイダーから電話会議の** 電話番号をソースにする

- **Microsoft 電話会議は地理的な場所では使用できません**

- 無料電話番号の使用や Teams 会議からサブスクリプションに含まれていない国の電話番号への発信通話など、分単位の支払いモデルを持つ電話会議サービスのオペレーターを利用する場合

## <a name="licensing-requirements-and-billing"></a>ライセンス要件と課金

開催する会議に参加するためにオペレーター Connect 会議番号が必要なユーザーには、Microsoft 電話会議 Standard サブスクリプションまたは Microsoft オペレーター Connect 会議ライセンスが割り当てられている必要があります。

### <a name="audio-conferencing-standard-subscription"></a>電話会議 Standard サブスクリプション

Microsoft 電話会議 Standard サブスクリプションは、Microsoft Teams ライセンスのアドオンとして購入できます。また、Microsoft 365 E5 および Office 365 E5 サブスクリプションにも含まれています。

電話会議 Standard サブスクリプションを使用すると、サブスクライバーは Microsoft の電話番号を使用し、オペレーターの番号を含む電話会議ブリッジを拡張できます。 サブスクライバーは、Microsoft 経由でルーティングする Teams会議からの発信通話と、オペレーターを介してルーティングする呼び出しを決定できます。

詳細については、「オペレーター会議の [**構成」Connect参照してください**](operator-connect-conferencing-configure.md)。

### <a name="operator-connect-conferencing-license"></a>オペレーター Connect会議ライセンス

Microsoft オペレーター Connect会議ライセンスは、そのライセンスのアドオンとしてMicrosoft Teamsできます。

オペレーター Connect会議ライセンスを使用すると、サブスクライバーはオペレーターの電話番号を使用できますが、Microsoft の電話番号は含まれます。 会議からのすべての発信Teamsオペレーターを介してルーティングする必要があります。

詳細については、「オペレーター会議の [**構成」Connect参照してください**](operator-connect-conferencing-configure.md)。

>[!Note]
>会議参加者は、オペレーター Connect 会議機能を持つユーザーが開催した会議に参加するために、電話会議標準サブスクリプション ライセンスまたはオペレーター Connect 会議ライセンスを必要としない。

オペレーター Connect 会議では、Microsoft は、組織で使用されている電話会議ライセンスの種類、Microsoft 電話会議またはオペレーター Connect 会議、および Microsoft が提供する電話番号の使用に従って組織に請求します。

オペレーターは、指定した電話会議番号に基Connectに対して組織に請求します。

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Microsoft 電話会議に関する追加情報

Microsoft 電話会議では、参加者は PSTN Microsoft Teamsでダイヤルインするか、PSTN 電話番号にダイヤルアウトして、会議に参加できます。 組織で使用できる Microsoft 電話会議機能の詳細については、「電話会議 」を参照[Microsoft 365。](audio-conferencing-in-office-365.md)
