---
title: PSTN を使用したハイブリッド環境のユーザー アカウント
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
description: ユーザー作成の異なる組み合わせと、サポートされている組み合わせまたはサポートされていない組み合わせについて学習します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d55f72bc9b22a3bb1e1ba889f24cf7a7ea0cbb53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096327"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>PSTN 接続を使用するハイブリッド環境でのユーザー アカウント

## <a name="about-the-environment"></a>環境について

この記事は、次のすべての環境を対象としています。 
 
- Skype for Business Server または Lync Server 2013 
- Microsoft 365 または Office 365 組織 
- Skype for Business Server と Skype for Business Online または Microsoft Teams テナントの間で構成されたハイブリッド接続 
- クライアントと PSTN (公衆交換電話網) 通話を発信および受信できるユーザー

 
別の環境 (Skype for Business Cloud Connector エディションなど) を使用している場合、ハイブリッドが構成されていない場合、またはユーザーが PSTN 通話を有効にしていない場合、サポート性マトリックスは異なります。  

## <a name="about-the-combinations-and-the-supportability-statement"></a>組み合わせとサポートに関する声明について  

PSTN 接続を備えた Skype for Business ハイブリッド環境は、ユーザー サービスが提供される場所とユーザー アカウントのプロビジョニングと管理方法に関する柔軟性を提供します。 しかし、多くのオプションでサポートされていない組み合わせが作成される可能性があります。 このセクションでは、ユーザー作成の異なる組み合わせと、サポートに関する声明について説明します。


**定義:**   
- **エンタープライズ VoIP:** オンプレミスの Skype for Business ユーザー アカウントを持つユーザーに PSTN へのアクセスを提供するオプション。 オンプレミスの Skype for Business 仲介サーバーは、PSTN との相互性を提供します。  
- **ハイブリッド音声接続:** Skype for Business Online アカウントを持つユーザーに PSTN へのアクセスを提供するオプション。 オンプレミスの Skype for Business 仲介サーバーは、PSTN との相互性を提供します。 
- **直接ルーティング:** Microsoft Teams クライアントを使用して、オンラインの Skype for Business アカウント、Microsoft Teams ライセンスを持つユーザーに PSTN へのアクセスを提供するオプション。 SBC は Microsoft 365 または Office 365 の SIP プロキシに接続され、Microsoft のオンプレミス ソフトウェアは必要とされていません。

  
**環境では、次の組み合わせをサポートしています。**
- **シナリオ 1:** オンプレミスの Skype for Business のユーザー アカウントであり、Skype for Business クライアントと一緒にエンタープライズ VoIP
- **シナリオ 2:** Skype for Business Online のユーザー アカウントで、ハイブリッド Voice Connectivity で Skype for Business クライアントを使用する
- **シナリオ 3:** Microsoft Teams ライセンスを持つ Skype for Business Online のユーザー アカウントであり、Teams クライアントを使用します。
 
### <a name="supportability-matrix"></a>サポート性マトリックス


|**作成したユーザー オブジェクト**  |**ユーザーの Skype for Business サービス プロバイダー**|**ユーザーのクライアント**|**音声オプション**|**サポート**|
| ------------ | --------- | --------- | --------- | -------- |
|オンプレミスのAD| オンプレミス |Skype for Business   | Enterprise Voice   |はい|
|オンプレミスのAD|オンライン| Skype for Business  | ハイブリッド音声接続   |はい |
|オンプレミスのAD|オンライン |Microsoft Teams |ダイレクト ルーティング  |はい |
|**サポートされていない組み合わせ**    | |         |         |      |
|Azure AD| オンプレミス/オンライン | Skype for Business/Microsoft Teams|エンタープライズ VoIP/ハイブリッド 音声接続/ダイレクト ルーティング  |いいえ、最初にユーザー オブジェクトをオンプレミスで作成するADがあります |
|オンプレミスのAD  |オンプレミス| Microsoft Teams| エンタープライズ VoIP/ハイブリッド 音声接続/ダイレクト ルーティング   |いいえ、Microsoft Teams クライアントはオンプレミスの Skype for Business ではサポートされていません |     
|オンプレミスのAD  |オンライン |Skype for Business  | ダイレクト ルーティング  |いいえ、直接ルーティングは Skype for Business クライアントではサポートされていません  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>PSTN を使用したハイブリッド環境のサポートに関する声明

すべてのユーザーの場合、ユーザーオブジェクトはオンプレミス AD で作成され、Azure AD Connect ツールを使用して Azure ADに同期する必要があります。 ユーザー オブジェクトが Azure ADハイブリッド構成で直接作成された場合、Teams/Skype for **Business** でユーザーを有効にすることはできません。 新入社員など、Teams で直接有効になる新規ユーザーの場合、ユーザーはオンプレミスの Skype for Business 管理ツールを使用して Skype for Business を有効にする必要があります。 オンラインの Skype for Business または Teams でユーザーを作成し、最初に Skype for Business と一緒にオンプレミス プールでユーザーを有効にエンタープライズ VoIP **はサポートされていません**。 詳細については、Skype for Business Server のオンプレミス PSTN 接続を使用した電話システムの計画 [に関するページを参照してください](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。