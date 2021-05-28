---
title: 演算子Connect
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
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
description: デプロイの要件や計画などConnectオペレーター の詳細を確認します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694542"
---
# <a name="plan-for-operator-connect"></a>オペレーター サービスのConnect

>[!NOTE]
>オペレーター Connectは、現在パブリック プレビューでのみ **使用できます**。 パブリック プレビューでは、今後の機能をテストし、フィードバックを提供できます。 パブリック プレビューに含まれる機能は、完全ではなく、変更される可能性があります。また、Office 365 Government Cloud ではサポートされていません。

オペレーター Connectは、PSTN (公衆交換電話網) と通信ネットワークとの間の接続を提供Teamsオプション電話システム。  

この記事では、メリットと要件について説明し、オペレーター プログラムに参加しているオペレーター Connectします。  組織に適切なソリューションConnect Operator Connect決定した場合は、この記事を読んだ後、「Configure Operator Connect 」を[参照してください](operator-connect-configure.md)。  

## <a name="benefits"></a>利点

オペレーター Connectを使用すると、既存のオペレーターが Microsoft Operator Connect プログラムに参加している場合、PSTN 通話を Teams に持ち込むサービスを管理できます。 Operator Connect プログラムには、次の利点があります。

- **既存のコントラクトを活用するか、新しい演算子を見つける。** 希望するオペレーターと契約を維持するか、ビジネス ニーズに合わせて、参加しているオペレーターの選択から新しいオペレーターを選択します。

- **オペレーターが管理するインフラストラクチャ。** オペレーターが PSTN 通話サービスとセッション ボーダー コントローラー (SBC) を管理し、ハードウェアの購入と管理を節約できます。

- **デプロイの高速化、簡単。** オペレーターにすばやく接続し、電話番号をユーザーに割り当て、管理センター Teamsできます。

- **サポートと信頼性の強化。** オペレーターは、サポート サービスを向上させるためにテクニカル サポートと共有サービス レベル アグリーメントを提供しますが、Azure を利用した直接ピアリングでは、信頼性を向上させるために 1 対 1 のネットワーク接続が作成されます。

## <a name="requirements"></a>要件

 オペレーター Connectは、次の場合に組織に適切なソリューションになる可能性があります。

- Microsoft 通話プランは、地理的な場所では利用できません。
- お好みのオペレーターは、Microsoft Operator Connectです。
- 新しい演算子を検索して、Teams で呼び出しを有効にする必要があります。

オペレーター アカウントで電話番号の割り当てを有効Connect、ユーザーが次の条件を持つ必要があります。

- Teams 電話ライセンスされています。 詳細については、「What [is 電話システム?」](what-is-phone-system-in-office-365.md)および「ユーザーに Teams アドオン ライセンスを割[り当てる」を参照してください](teams-add-on-licensing/assign-teams-add-on-licenses.md)。
- TeamsOnly モード。 詳細については、「共存と相互[運用性Microsoft TeamsとSkype for Businessを理解する」を参照してください](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

## <a name="available-operators"></a>使用可能な演算子

次の演算子は、Microsoft Operator Connectプログラムの参加者です。

| オペレーター | 機能 | 国の対象範囲 |
| --- | --- | --- |
| `BT`  | 通話 | ベルギー、デンマーク、フィンランド、フランス、ドイツ、アイルランド、イタリア、ルクセンブルク、オランダ、ノルウェー、ポーランド、南アフリカ、スペイン、スウェーデン、スイス、英国 |
| `Intrado` | 通話 | ベルギー、カナダ、デンマーク、フランス、ドイツ、アイルランド、ルクセンブルク、オランダ、スペイン、スウェーデン、英国、米国  |
| `NTT`  | 通話 | オーストリア、ベルギー、ブラジル、カナダ、チェコ、デンマーク、フィンランド、フランス、ドイツ、アイルランド、イタリア、ルクセンブルク、メキシコ、オランダ、ノルウェー、ポーランド、ポルトガル、プエルトリコ、ルーマニア、南アフリカ、スペイン、スウェーデン、スイス、英国、米国 |
| `NuWave` | 通話 | オーストリア、ベルギー、カナダ、デンマーク、フランス、ドイツ、アイルランド、イタリア、オランダ、ポルトガル、スペイン、スウェーデン、スイス、英国、米国   |
| `Orange Business Services` | 通話 | オーストリア、ベルギー、チェコ、デンマーク、フィンランド、フランス、ギアナ、ドイツ、グアドループ、アイルランド、イタリア、ルクセンブルク、マルチニーク、マヨット、オランダ、ノルウェー、ポーランド、ポルトガル、レウニオン、サン・バルテレンティ、サン・マルタン、スペイン、スバルバルド、スウェーデン、スイス、英国  |
| `Pure IP` | 通話 | オーストラリア、オーストリア、ベルギー、ブラジル、ブルガリア、カナダ、チリ、コロンビア、クロアチア、キプロス、チェコ、デンマーク、フィンランド、フランス、ドイツ、ギリシャ、香港ドル、ギリシャ、アイルランド、イタリア、日本、リトアニア、ルクセンブルク、マレーシア、メキシコ、オランダ、ニュージーランド、ノルウェー、ブラジル、ポルトガル、プエルトリコ、ルーマニア、シンガポール、スロバキア、スロベニア、南アフリカ、スペイン、スウェーデン、スイス、英国、米国  |
| `Rogers Business` | 通話 | カナダ  |
| `TATA Communications` | 通話 | オーストラリア、オーストリア、ベルギー、カナダ、チェコシア、デンマーク、フランス、ドイツ、香港国際航空、ハンガリー、アイルランド、イタリア、マレーシア、メキシコ、オランダ、ニュージーランド、ポーランド、ポルトガル、ルーマニア、シンガポール、韓国、スペイン、スウェーデン、スイス、タイ、英国、米国 |
| `Telekom Deutschland` | 通話 | ドイツ  |
| `Telenor` | 通話 | デンマーク、フィンランド、ノルウェー、スウェーデン  |
| `Verizon` | 通話 | 米国 |
