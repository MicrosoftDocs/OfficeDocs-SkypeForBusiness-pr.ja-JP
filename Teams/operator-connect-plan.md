---
title: オペレーター接続
author: CarolynRowe
ms.author: crowe
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
description: オペレーター接続について詳しくは、要件やデプロイの計画などをご覧ください。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 745587281c5566b1ba4fe0d1ea06a44d40c8a7f2
ms.sourcegitcommit: 5a8a077b30a0eab2342afc422869adaa682a015b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66915185"
---
# <a name="plan-for-operator-connect"></a>オペレーター接続の計画

オペレーター接続は、Teams と電話システムとの公衆交換電話網 (PSTN) 接続を提供するためのもう 1 つのオプションです。 Teams 音声ソリューションと PSTN 接続オプションの詳細については、「 [Teams 音声ソリューション](cloud-voice-landing-page.md) と [PSTN 接続オプション](pstn-connectivity.md)を計画する」を参照してください。

この記事では、利点と要件について説明し、Microsoft Operator Connect Program に参加しているオペレーターへのリンクを提供します。  オペレーター接続が組織に適したソリューションであると判断した場合は、この記事を読んだ後の [オペレーター接続の構成に関するページを](operator-connect-configure.md)参照してください。  

## <a name="benefits"></a>利点

オペレーター接続を使用すると、既存のオペレーターが Microsoft オペレーター接続プログラムの参加者である場合、PSTN 通話を Teams に呼び出すためのサービスを管理できます。 オペレーター接続プログラムには、次の利点があります。

- **既存のコントラクトを活用するか、新しい演算子を見つけます。** 希望するオペレーターと契約を保持するか、ビジネス ニーズを満たすために参加しているオペレーターの選択から新しいオペレーターを選択します。

- **オペレーターが管理するインフラストラクチャ。** オペレーターは PSTN 通話サービスとセッション ボーダー コントローラー (SBC) を管理し、ハードウェアの購入と管理を節約できます。

- **デプロイを高速化し、簡単に行います。** オペレーターにすばやく接続し、ユーザーに電話番号を割り当てることができます。すべて Teams 管理センターからアクセスできます。

- **サポートと信頼性の強化。** オペレーターは、サポート サービスを向上させるためにテクニカル サポートと共有サービス レベル アグリーメントを提供しますが、Azure を利用した直接ピアリングでは、信頼性を高めるために 1 対 1 のネットワーク接続が作成されます。

## <a name="requirements"></a>要件

 次の場合は、オペレーター接続が組織に適したソリューションである可能性があります。

- Microsoft 通話プランは、地理的な場所では利用できません。
- 優先オペレーターは、Microsoft オペレーター接続プログラムの参加者です。
- Teams で呼び出しを有効にする新しいオペレーターを見つける必要があります。

Operator Connect で電話番号の割り当てを有効にするには、ユーザーが次のユーザーであることを確認します。

- Teams Phone のライセンスが付与されています。 詳細については、「 [電話システムとは」](what-is-phone-system-in-office-365.md) と「 [Teams アドオン ライセンスをユーザーに割り当てる」を](teams-add-on-licensing/assign-teams-add-on-licenses.md)参照してください。
- TeamsOnly モード。 ユーザーは TeamsOnly モードである必要がありますが、組織全体ではそうではありません。 詳細については、「[Microsoft Teams について理解し、共存と相互運用性をSkype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)する」を参照してください。

Microsoft Operator Connect Program に参加しているオペレーターとそのサービスが利用可能な国または地域の一覧については、 [Microsoft 365 Operator Connect ディレクトリ](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)を参照してください。
