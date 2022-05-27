---
title: PSTN を使用したハイブリッド環境のユーザー アカウント
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: ユーザー作成のさまざまな組み合わせと、サポートされている組み合わせまたはサポートされていない組み合わせについて説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97d1a3ac433db78792ca3cc512d32c5a8fec243
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676419"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>PSTN 接続を使用するハイブリッド環境でのユーザー アカウント

## <a name="about-the-environment"></a>環境について

この記事は、次のすべてが含まれる環境に適用されます。

- Skype for Business Serverまたは Lync Server 2013
- Microsoft 365またはOffice 365組織
- Skype for Business Serverと Skype for Business Online または Microsoft Teams テナントの間で構成されたハイブリッド接続
- クライアントとの間で公衆交換電話網 (PSTN) 呼び出しの発信と受信を有効にしているユーザー


別の環境 (Skype for Business クラウド コネクタ エディションなど) がある場合、ハイブリッドが構成されていない場合、またはユーザーが PSTN 通話を有効にしていない場合、サポート可能性マトリックスは異なります。

## <a name="about-the-combinations-and-the-supportability-statement"></a>組み合わせとサポート性に関するステートメントについて

PSTN 接続を備えたSkype for Businessハイブリッド環境では、ユーザー サービスを提供する場所と、ユーザー アカウントのプロビジョニングと管理方法に関する柔軟性が提供されます。 しかし、豊富なオプションによって、サポートされていない組み合わせが作成される可能性があります。 このセクションでは、ユーザー作成のさまざまな組み合わせと、サポート性に関する声明について説明します。

**定義：**

- **エンタープライズ VoIP:** オンプレミス Skype for Business ユーザー アカウントを持つユーザーに PSTN へのアクセスを提供するオプション。 オンプレミスのSkype for Business仲介サーバーは、PSTN への相互接続性を提供します。
- **ハイブリッド音声接続:** Skype for Business Online アカウントを持つユーザーに PSTN へのアクセスを提供するオプション。 オンプレミスのSkype for Business仲介サーバーは、PSTN への相互接続性を提供します。
- **ダイレクト ルーティング:** Microsoft Teams クライアントを使用して、オンライン Skype for Business アカウント、Microsoft Teams ライセンスを持つユーザーに PSTN へのアクセスを提供するオプション。 SBC は、Microsoft のオンプレミス ソフトウェアを必要とせずに、Microsoft 365またはOffice 365で SIP プロキシに接続されます。

**環境では、次の組み合わせがサポートされています。**

- **シナリオ 1:** オンプレミスSkype for Businessユーザー アカウントであり、エンタープライズ VoIPでSkype for Business クライアントを使用します
- **シナリオ 2:** オンラインでのビジネス向けのSkypeのユーザー アカウント。Hybrid Voice Connectivity でSkype for Business クライアントを使用します
- **シナリオ 3:** Microsoft Teams ライセンスを使用してオンラインでSkype for Businessのユーザー アカウントTeamsクライアントを使用します

### <a name="supportability-matrix"></a>サポート可能性マトリックス

|で作成されたユーザー オブジェクト|ユーザーのSkype for Business サービス プロバイダー|ユーザーのクライアント|音声オプション|サポート|
|---|---|---|---|---|
|オンプレミス AD|オンプレミス|Skype for Business|Enterprise Voice|Yes|
|オンプレミス AD|オンライン|Skype for Business|ハイブリッド音声接続|Yes|
|オンプレミス AD|オンライン|Microsoft Teams|ダイレクト ルーティング|はい|
|**サポートされていない組み合わせ**|||||
|Azure AD|オンプレミス/オンライン|Skype for Business/Microsoft Teams|エンタープライズ VoIP/ハイブリッド音声接続/ダイレクト ルーティング|いいえ。ユーザー オブジェクトは、最初にオンプレミス AD で作成する必要があります|
|オンプレミス AD|オンプレミス|Microsoft Teams|エンタープライズ VoIP/ハイブリッド音声接続/ダイレクト ルーティング|いいえMicrosoft TeamsクライアントはオンプレミスのSkype for Businessではサポートされていません|
|オンプレミス AD|オンライン|Skype for Business|ダイレクト ルーティング|いいえ。ダイレクト ルーティングは、Skype for Business クライアントではサポートされていません|

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>PSTN を使用したハイブリッド環境のサポート性に関する声明

すべてのユーザーに対して、ユーザー オブジェクトをオンプレミス AD で作成し、Azure AD Connect ツールを使用して Azure AD に同期する **必要があります**。 ユーザー オブジェクトがハイブリッド構成で Azure AD に直接作成されている場合、ユーザーのTeams/Skype for Businessの有効化は **サポートされません**。 新入社員など、Teamsに対して直接有効にする新しいユーザーの場合、ユーザーはオンプレミスのSkype for Business管理ツールを使用してSkype for Businessを有効にする必要があります。 オンライン Skype for BusinessまたはTeamsでのユーザーの作成は、最初にエンタープライズ VoIPを使用してオンプレミス プールでユーザーを有効に **することはサポートされていません**。 詳細については、[Skype for Business Serverのオンプレミス PSTN 接続を使用した電話システムの計画に関する説明を参照](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)してください。
