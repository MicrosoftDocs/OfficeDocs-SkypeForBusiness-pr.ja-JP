---
title: PSTN 接続を使用するハイブリッド環境でのユーザー アカウント
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: ユーザーの作成」と「どの組み合わせがサポートまたはサポートされていないのさまざまな組み合わせについて説明します。
ms.openlocfilehash: aaaf06fd0f4e697a1a4c371a9030510b9708f171
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298541"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>PSTN 接続を使用するハイブリッド環境でのユーザー アカウント

## <a name="about-the-environment"></a>環境について

この資料は、次のある環境に適用されます。 
 
- Skype ビジネス サーバーまたは Lync Server 2013 の 
- Office 365 テナント 
- ビジネス サーバーの Skype と Skype ビジネス オンラインまたはマイクロソフトのチームのテナントの間で構成されているハイブリッド接続 
- クライアントとの間の公衆交換電話網 (PSTN) 通話を送受信するを有効にするユーザー

 
ビジネス クラウド コネクタ ・ エディションの Skype) などのさまざまな環境、ハイブリッドが構成されていない場合や、ユーザーが PSTN 通話を有効になっていない、さまざまなサポート ・ マトリックスになります。  

## <a name="about-the-combinations-and-the-supportability-statement"></a>組み合わせとサポート性のステートメントについて  

PSTN への接続でのビジネスのハイブリッド環境に、Skype では、ユーザー サービスを提供する場所と、ユーザー アカウントのプロビジョニングし管理の方法に関する柔軟性を提供します。 ですが、豊富なオプションがいくつかサポートされていない組み合わせを作成可能性があります。 このセクションでは、サポート性のステートメントの後に、ユーザーの作成のさまざまな組み合わせについて説明します。


**定義:**   
- **エンタープライズ VoIP:** ビジネス ・ ユーザー ・ アカウントの設置型の Skype でのユーザーに PSTN にアクセスを提供するオプションです。 ビジネス仲介サーバーの設置型の Skype は、PSTN への相互接続性を提供します。  
- **ハイブリッド音声接続:** PSTN に Skype でのビジネスのオンライン アカウントのユーザーのアクセスを提供するオプションです。 ビジネス仲介サーバーの設置型の Skype は、PSTN への相互接続性を提供します。 
- **ルーティングの指示:** マイクロソフト チームのクライアントを使用してオンラインの Skype ビジネス アカウントでは、マイクロソフトのチームのライセンスを持つユーザーは PSTN へのアクセスを提供するオプションです。 SBC に接続されている Office 365 の SIP プロキシのオンプレミス ソフトウェアがなくても Microsoft から。

  
**環境には、以下の組み合わせがサポートされています。**
- **シナリオ 1:** ユーザーは、設置型のビジネスでは、Skype アカウントし、エンタープライズ VoIP を使用するビジネス クライアント用の Skype を使用
- **シナリオ 2:** ユーザーは、オンライン ビジネスの Skype のアカウントし、ハイブリッドの音声接続を備えたビジネス クライアント用の Skype を使用
- **シナリオ 3:** ユーザーは、マイクロソフトのチームのライセンスを使用したオンライン ビジネスの Skype のアカウントし、チームのクライアントを使用
 
### <a name="supportability-matrix"></a>サポート ・ マトリックス


|**作成されたユーザー オブジェクト**  |**ビジネス ・ サービス ・ プロバイダーのユーザーの Skype**|**ユーザーのクライアント**|**音声オプション**|**サポート対象**|
| ------------ | --------- | --------- | --------- | -------- |
|オンプレミス AD| オンプレミス |Skype for Business   | エンタープライズ VoIP   |はい|
|オンプレミス AD|オンライン| Skype for Business  | ハイブリッド音声接続   |はい |
|オンプレミス AD|オンライン |Microsoft Teams |ダイレクト ルーティング  |はい |
|**サポートされていない組み合わせ**    | |         |         |      |
|Azure AD| 設置型またはオンラインで | Skype ビジネスと Microsoft のチームの|接続または直接ルーティングするエンタープライズ VoIP/ハイブリッド音声  |ユーザー オブジェクトを作成する必要がなく、オンプレミス AD 最初 |
|オンプレミス AD  |オンプレミス| Microsoft Teams| 接続または直接ルーティングするエンタープライズ VoIP/ハイブリッド音声   |残念ですが、マイクロソフトのチームのクライアントは、ビジネスのためのオンプレミス Skype でサポートされていません |     
|オンプレミス AD  |オンライン |Skype for Business  | ダイレクト ルーティング  |残念ですが、直接ルーティングではサポートされておらず Skype でビジネスのクライアントに、ユーザーは、最初にビジネス用の Skype でエンタープライズ VoIP に対して有効にする必要があります。  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>PSTN のハイブリッド環境のサポート ステートメント

**必要があります**が、ユーザーのすべてのユーザーのオブジェクト設置型で、作成する AD Azure AD 接続ツールを使用した Azure AD に同期するとします。 ユーザーの有効化なチームと Skype ビジネスは**サポートされていません**のハイブリッド構成では、Azure AD で直接ユーザー オブジェクトが作成されている場合。 など、新入社員、チームに対して直接有効にするは、ユーザーの新しいユーザーのユーザーする必要があります有効にする Skype のビジネス Skype の社内業務管理ツールを使用します。 最初を有効にするエンタープライズ VoIP の**サポートされていない**とプールを設置せず、ビジネスまたはチームのオンライン Skype でユーザーを作成しています。 詳細については、 [Skype のビジネス サーバーの PSTN への接続をオンプレミスと Office 365 の電話システムの計画](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)を参照してください。
