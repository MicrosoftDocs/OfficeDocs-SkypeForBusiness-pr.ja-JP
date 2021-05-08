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
description: ユーザー作成のさまざまな組み合わせと、サポートされている組み合わせまたはサポートされていない組み合わせについて学習します。
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

この記事は、次のすべての環境に適用されます。 
 
- Skype for Business Server Lync Server 2013 
- 組織Microsoft 365またはOffice 365組織 
- Skype for Business Server と Skype for Business Online または Microsoft Teams テナントの間で構成されたハイブリッド接続 
- クライアントに対する公衆交換電話網 (PSTN) 通話の発信と受信が有効になっているユーザー

 
別の環境 (Skype for Business クラウド コネクタ エディション など) がある場合、ハイブリッドが構成されていない場合、またはユーザーが PSTN 通話を有効にしていない場合、サポートマトリックスは異なります。  

## <a name="about-the-combinations-and-the-supportability-statement"></a>組み合わせとサポート可能性に関する声明について  

PSTN Skype for Businessハイブリッド環境では、ユーザー サービスが提供される場所と、ユーザー アカウントのプロビジョニングと管理方法に関する柔軟性が提供されます。 ただし、オプションが多く存在すると、サポートされていない組み合わせが作成される可能性があります。 このセクションでは、ユーザー作成のさまざまな組み合わせと、サポートに関する声明について説明します。


**定義:**   
- **エンタープライズ VoIP:** オンプレミスのユーザー アカウントを持つユーザーに PSTN へのアクセスSkype for Businessオプション。 オンプレミスの仲介サーバー Skype for Business PSTN への相互接続を提供します。  
- **ハイブリッド音声接続:** オンライン アカウントを持つユーザーに PSTN へのアクセスSkype for Businessオプション。 オンプレミスの仲介サーバー Skype for Business PSTN への相互接続を提供します。 
- **直接ルーティング:** オンライン アカウントを持つユーザーに PSTN へのアクセスSkype for Business、Microsoft Teamsクライアントを使用Microsoft Teamsオプション。 SBC は、Microsoft のオンプレミス ソフトウェアを必要とせずに、Microsoft 365 または Office 365 の SIP プロキシに接続されます。

  
**環境では、次の組み合わせをサポートしています。**
- **シナリオ 1:** オンプレミスのSkype for Business アカウント。オンプレミスのユーザー アカウントSkype for Businessクライアントを使用エンタープライズ VoIP
- **シナリオ 2:** オンラインで一Skypeのユーザー アカウント。ハイブリッド音声接続で Skype for Business クライアントを使用します。
- **シナリオ 3:** ライセンスを使用Skype for Businessオンラインのユーザー アカウントMicrosoft Teamsクライアントを使用Teamsします。
 
### <a name="supportability-matrix"></a>サポートのマトリックス


|**で作成されたユーザー オブジェクト**  |**ユーザーの Skype for Business サービス プロバイダー**|**ユーザーのクライアント**|**音声オプション**|**サポート**|
| ------------ | --------- | --------- | --------- | -------- |
|オンプレミスのAD| オンプレミス |Skype for Business   | Enterprise Voice   |はい|
|オンプレミスのAD|オンライン| Skype for Business  | ハイブリッド音声接続   |はい |
|オンプレミスのAD|オンライン |Microsoft Teams |ダイレクト ルーティング  |はい |
|**サポートされていない組み合わせ**    | |         |         |      |
|Azure AD| オンプレミス/オンライン | Skype for Business/Microsoft Teams|エンタープライズ VoIP/ハイブリッド音声接続/ダイレクト ルーティング  |いいえ。ユーザー オブジェクトは、最初にオンプレミスに作成するAD必要があります |
|オンプレミスのAD  |オンプレミス| Microsoft Teams| エンタープライズ VoIP/ハイブリッド音声接続/ダイレクト ルーティング   |いいえ、Microsoft Teamsクライアントは、オンプレミスのクライアントではサポートSkype for Business |     
|オンプレミスのAD  |オンライン |Skype for Business  | ダイレクト ルーティング  |いいえ、直接ルーティングはクライアントでSkype for Businessされていません  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>PSTN を使用したハイブリッド環境のサポート可能性に関する声明

すべてのユーザーについて、ユーザー オブジェクトをオンプレミスの AD に作成し、Azure AD Connect ツールを使用して Azure AD に同期する必要があります。 ユーザー オブジェクトがハイブリッド構成Teams Azure ADで直接作成されている場合、Teams/Skype for Business のユーザーの有効化はサポートされていません。 Teams に対して直接有効になる新入社員などの新しいユーザーの場合、ユーザーはオンプレミスの Skype for Business 管理ツールを使用して Skype for Business に対して有効にする必要があります。 ユーザーをオンライン Skype for Business または Teams でオンプレミス プールで有効にせずに作成エンタープライズ VoIP **はサポートされていません**。 詳細については、「オンプレミスの[PSTN](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)接続を使用電話システムの計画」を参照Skype for Business Server。