---
title: オペレーター接続
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 09/30/2021
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
description: オペレーター接続の詳細 (要件やデプロイの計画など) について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf1e158eb491f0b4b4f2df19c4aa7ebe46f08950
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249669"
---
# <a name="plan-for-operator-connect"></a>オペレーター接続の計画

オペレーター接続は、Teamsと電話システムに公衆交換電話網 (PSTN) 接続を提供するためのもう 1 つのオプションです。 Teams音声ソリューションと PSTN 接続オプションの詳細については、「[Teams音声ソリューション](cloud-voice-landing-page.md)と [PSTN 接続オプション](pstn-connectivity.md)を計画する」を参照してください。

この記事では、利点と要件について説明し、Microsoft オペレーター接続 プログラムに参加しているオペレーターへのリンクを提供します。  組織に適したソリューションオペレーター接続決定した場合は、この記事を読んだ後、「[オペレーター接続の構成」を](operator-connect-configure.md)参照してください。  

## <a name="benefits"></a>利点

オペレーター接続を使用すると、既存のオペレーターが Microsoft オペレーター接続 プログラムの参加者である場合、PSTN 通話をTeamsに持ち込むサービスを管理できます。 オペレーター接続 プログラムには、次の利点があります。

- **既存のコントラクトを活用するか、新しい演算子を見つけます。** 希望するオペレーターと契約を保持するか、ビジネス ニーズを満たすために参加しているオペレーターの選択から新しいオペレーターを選択します。

- **オペレーターが管理するインフラストラクチャ。** オペレーターは PSTN 通話サービスとセッション ボーダー コントローラー (SBC) を管理し、ハードウェアの購入と管理を節約できます。

- **デプロイを高速化し、簡単に行います。** オペレーターにすばやく接続し、電話番号をユーザーに割り当てることができます(すべてTeams管理センターから)。

- **サポートと信頼性の強化。** オペレーターは、サポート サービスを向上させるためにテクニカル サポートと共有サービス レベル アグリーメントを提供しますが、Azure を利用した直接ピアリングでは、信頼性を高めるために 1 対 1 のネットワーク接続が作成されます。

## <a name="requirements"></a>要件

 オペレーター接続は、次の場合に組織に適したソリューションである可能性があります。

- Microsoft 通話プランは、地理的な場所では利用できません。
- 優先演算子は、Microsoft オペレーター接続 プログラムの参加者です。
- Teamsでの呼び出しを有効にする新しい演算子を見つける必要があります。

オペレーター接続で電話番号の割り当てを有効にするには、ユーザーが次のユーザーであることを確認します。

- ライセンスTeams 電話。 詳細については、「[電話システムとは」](what-is-phone-system-in-office-365.md)と「ユーザーに[アドオン ライセンスTeams割り当てる」を](teams-add-on-licensing/assign-teams-add-on-licenses.md)参照してください。
- TeamsOnly モード。 ユーザーは TeamsOnly モードである必要がありますが、組織全体ではそうではありません。 詳細については、「[Microsoft TeamsとSkype for Business共存と相互運用性について理解](teams-and-skypeforbusiness-coexistence-and-interoperability.md)する」を参照してください。

Microsoft オペレーター接続 プログラムに参加しているオペレーターとそのサービスが利用可能な国または地域の一覧については、[Microsoft 365 オペレーター接続 ディレクトリ](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)を参照してください。
