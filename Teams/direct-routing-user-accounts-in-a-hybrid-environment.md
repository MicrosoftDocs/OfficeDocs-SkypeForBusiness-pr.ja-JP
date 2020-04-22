---
title: PSTN を使用したハイブリッド環境のユーザーアカウント
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: ユーザー作成のさまざまな組み合わせと、サポートされている組み合わせとサポートされていない組み合わせについて説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a235b5c27919c0015849140a3e772f4a189a17d8
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779996"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>PSTN 接続を使用するハイブリッド環境でのユーザー アカウント

## <a name="about-the-environment"></a>環境について

この記事は、次の項目をすべて使用している環境に適用されます。 
 
- Skype for Business Server または Lync Server 2013 
- Office 365 組織 
- Skype for Business Server と Skype for business Online または Microsoft Teams テナント間で構成されたハイブリッド接続 
- クライアントとの間での公衆交換電話網 (PSTN) 通話の発信と受信を有効にしているユーザー

 
別の環境 (Skype for Business Cloud Connector Edition など) がある場合、ハイブリッドが構成されていない場合、または PSTN 通話を有効にしていない場合は、サポートされているマトリックスとは異なります。  

## <a name="about-the-combinations-and-the-supportability-statement"></a>組み合わせとサポートについて  

PSTN 接続を使用した Skype for Business ハイブリッド環境では、ユーザーサービスが提供される場所と、ユーザーアカウントをプロビジョニングおよび管理する方法に関して柔軟性が提供されます。 ただし、豊富なオプションを選択すると、サポートされていない組み合わせがある場合があります。 このセクションでは、ユーザー作成のさまざまな組み合わせについて説明します。その後でサポートステートメントを示します。


**構造**   
- **エンタープライズ voip:** オンプレミスの Skype for Business ユーザーアカウントを使用するユーザーの PSTN へのアクセスを提供するオプション。 オンプレミスの Skype for Business 仲介サーバーは、PSTN との相互に対応しています。  
- **ハイブリッド音声接続:** Skype for Business Online アカウントを持つユーザーに PSTN へのアクセスを提供するオプション。 オンプレミスの Skype for Business 仲介サーバーは、PSTN との相互に対応しています。 
- **直接ルーティング:** オンラインの Skype for Business アカウント、Microsoft Teams のライセンスを持つユーザーに対して、Microsoft Teams クライアントを使って PSTN へのアクセスを提供するオプション。 SBC は、Microsoft のオンプレミスソフトウェアを必要とせずに、Office 365 の SIP プロキシに接続されています。

  
**環境では、次の組み合わせがサポートされています。**
- **シナリオ 1:** Skype for Business オンプレミスのユーザーアカウントとエンタープライズ Voip の Skype for Business クライアントを使用する
- **シナリオ 2:** Skype for business online のユーザーアカウントとハイブリッド音声接続を使用する Skype for Business クライアントを使用する
- **シナリオ 3:** Microsoft Teams ライセンスを使用する Skype for Business online のユーザーアカウントとチームクライアントを使用する
 
### <a name="supportability-matrix"></a>サポート性マトリックス


|**ユーザーオブジェクトの作成日時**  |**ユーザーの Skype for Business サービスプロバイダ**|**ユーザーのクライアント**|**音声オプション**|**サポート**|
| ------------ | --------- | --------- | --------- | -------- |
|オンプレミス広告| オンプレミス |Skype for Business   | Enterprise Voice   |はい|
|オンプレミス広告|オンライン| Skype for Business  | ハイブリッドボイス接続   |はい |
|オンプレミス広告|オンライン |Microsoft Teams |ダイレクト ルーティング  |はい |
|**サポートされていない組み合わせ**    | |         |         |      |
|Azure AD| オンプレミス/オンライン | Skype for Business/Microsoft Teams|エンタープライズ音声/ハイブリッドボイス接続/直接ルーティング  |いいえ。オンプレミスの広告では、最初にユーザーオブジェクトを作成する必要があります |
|オンプレミス広告  |オンプレミス| Microsoft Teams| エンタープライズ音声/ハイブリッドボイス接続/直接ルーティング   |いいえ、Microsoft Teams クライアントはオンプレミスの Skype for Business ではサポートされていません |     
|オンプレミス広告  |オンライン |Skype for Business  | ダイレクト ルーティング  |いいえ。 skype for business クライアントでは、直接ルーティングはサポートされておらず、Skype for Business では、ユーザーはエンタープライズ Voip を有効にしておく必要があります。  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>PSTN を使ったハイブリッド環境のサポートに関する声明

すべてのユーザーについて、ユーザーオブジェクトはオンプレミスの AD で作成し、Azure AD Connect ツールを使用して Azure AD に同期する**必要があり**ます。 ユーザーオブジェクトがハイブリッド構成で Azure AD で直接作成されている場合は、Teams または Skype for Business のユーザーを有効にする**ことはできません**。 新規採用された新入社員など、Teams で直接有効になる新しいユーザーの場合、オンプレミスの Skype for Business 管理ツールを使用して Skype for Business のユーザーを有効にする必要があります。 エンタープライズボイスを使用して、オンプレミスのプールでユーザーを初めて有効にすることなく、オンラインの Skype for Business または Teams でユーザーを作成すること**はサポートされません**。 詳細については、「 [Office 365 のプラン電話システムと Skype For Business Server のオンプレミスの PSTN 接続を](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)確認する」を参照してください。
