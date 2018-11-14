---
title: PSTN への接続を持つハイブリッド環境でのユーザー アカウント
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: ユーザーの作成」と「どの組み合わせがサポートまたはサポートされていないのさまざまな組み合わせについて説明します。
ms.openlocfilehash: f742efc18de05997f73a33b96800cc10a9a9d124
ms.sourcegitcommit: 5d8b5dee1dea84494aea92bbce568dea10752af9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "26510623"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>PSTN への接続を持つハイブリッド環境でのユーザー アカウント

## <a name="about-the-environment"></a>環境について

この資料は、次のある環境に適用されます。 
 
- Skype ビジネス サーバーまたは Lync Server 2013 の 
- Office 365 テナント 
- ビジネス サーバーの Skype と Skype ビジネス オンラインまたはマイクロソフトのチームのテナントの間で構成されているハイブリッド接続 
- クライアントとの間の公衆交換電話網 (PSTN) 通話を送受信するを有効にするユーザー

 
ビジネス クラウド コネクタ ・ エディションの Skype) などのさまざまな環境、ハイブリッドが構成されていない場合や、ユーザーが PSTN の呼び出しは無効になります、さまざまなサポート ・ マトリックスになります。  

## <a name="about-the-combinations-and-the-supportability-statement"></a>組み合わせとサポート性のステートメントについて  

PSTN への接続でのビジネスのハイブリッド環境に、Skype では、ユーザー サービスを提供する場所と、ユーザー アカウントのプロビジョニングし管理の方法に関する柔軟性を提供します。 ですが、豊富なオプションがいくつかサポートされていない組み合わせを作成可能性があります。 このセクションでは、サポート性のステートメントの後に、ユーザーの作成のさまざまな組み合わせについて説明します。


**定義:**   
- **エンタープライズ VoIP:** ビジネス ・ ユーザー ・ アカウントの設置型の Skype でのユーザーに PSTN にアクセスを提供するオプションです。 ビジネス仲介サーバーの設置型の Skype は、PSTN への相互接続性を提供します。  
- **ハイブリッド音声接続:** ビジネス アカウントの Skype のオンラインでの PSTN へのアクセスを提供するオプションです。 ビジネス仲介サーバーの設置型の Skype は、PSTN への相互接続性を提供します。 
- **ルーティングの指示:** マイクロソフト チームのクライアントを使用してオンラインの Skype ビジネス アカウントでは、マイクロソフトのチームのライセンスを持つユーザーは PSTN へのアクセスを提供するオプションです。 SBC に接続されている Office 365 の SIP プロキシのオンプレミス ソフトウェアがなくても Microsoft から。

  
**環境には、以下の組み合わせがサポートされています。**
- **シナリオ 1:** ユーザーが社内のビジネスのための Skype アカウントし、エンタープライズ VoIP を使用するビジネス クライアント用の Skype を使用
- **シナリオ 2:** ユーザーは、オンライン ビジネスの Skype のアカウントし、ハイブリッドの音声接続を備えたビジネス クライアント用の Skype を使用
- **シナリオ 3:** ユーザーは、マイクロソフトのチームのライセンスを使用したオンライン ビジネスの Skype のアカウントし、チームのクライアントを使用
 
### <a name="supportability-matrix"></a>サポート ・ マトリックス


|**作成されたユーザー オブジェクト**  |**ビジネス ・ サービス ・ プロバイダーのユーザーの Skype**|**ユーザーのクライアント**|**音声オプション**|**サポート対象**|
|---------|---------|---------|---------|--------|
|オンプレミス AD| オンプレミス |Skype for Business   | エンタープライズ VoIP   |あり|
|オンプレミス AD|オンライン| Skype for Business  | ハイブリッド音声接続   |あり |
|オンプレミス AD|オンライン |Microsoft Teams |直接のルーティング  |あり |
|**サポートされていない組み合わせ**    | |         |         |
|Azure AD| 設置型またはオンラインで | Skype ビジネスと Microsoft のチームの|接続または直接ルーティングするエンタープライズ VoIP/ハイブリッド音声  |ユーザー オブジェクトを作成する必要がなく、オンプレミス AD 最初 |
|オンプレミス AD  |オンプレミス| Microsoft Teams| 接続または直接ルーティングするエンタープライズ VoIP/ハイブリッド音声   |残念ですが、マイクロソフトのチームのクライアントは、ビジネスのためのオンプレミス Skype でサポートされていません |
|オンプレミス AD  |オンライン |Skype for Business | 直接のルーティング  | いいえ、ビジネス クライアント用の Skype は、直接ルーティングでサポートされていません  |
|オンプレミス AD  |オンライン |Skype for Business  | 直接のルーティング  |残念ですが、直接ルーティングではサポートされておらず Skype でビジネスのクライアントに、ユーザーは、最初にビジネス用の Skype でエンタープライズ VoIP に対して有効にする必要があります。  |
|   |         |         |         ||

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>PSTN のハイブリッド環境のサポート ステートメント

**必要があります**が、ユーザーのすべてのユーザーのオブジェクト設置型で、作成する AD Azure AD 接続ツールを使用した Azure AD に同期するとします。 ユーザーの有効化なチームと Skype ビジネスは**サポートされていません**のハイブリッド構成では、Azure AD で直接ユーザー オブジェクトが作成されている場合。 など、新入社員、チームに対して直接有効にするは、ユーザーの新しいユーザーには、オンプレミス Skype のビジネス管理ツールを使用してビジネスの Skype のユーザーを有効にする必要があります。 最初を有効にするエンタープライズ VoIP の**サポートされていない**とプールを設置せず、ビジネスまたはチームのオンライン Skype でユーザーを作成しています。 ハイブリッド構成で、ビジネスの Skype のユーザーを有効にする方法の詳細については[この資料](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises#special-considerations-when-enabling-users-for-enterprise-voice-on-premises)を参照してください。
