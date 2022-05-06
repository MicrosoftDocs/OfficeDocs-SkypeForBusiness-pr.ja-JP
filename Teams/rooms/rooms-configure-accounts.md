---
title: Microsoft Teams Rooms のアカウントを構成する
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: このトピックでは、Microsoft Teams Rooms (Surface Hubを含む) と共通エリア電話のアカウントの構成について説明します。
ms.openlocfilehash: 4ecac71ef862fda003523bbcefe3c333daefaa23
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514732"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Microsoft Teams Rooms のアカウントを構成する
 
このトピックでは、Microsoft Teams Roomsによって使用されるアカウントを作成する方法について説明します。 インフラストラクチャは、次のいずれかの構成に分類されます。
  
- オンライン展開: 組織の環境全体が Microsoft 365 または Office 365 に展開されます。
    
- オンプレミス展開: 組織に、Active Directory、Exchange、Skype for Business Server がどこでホストされるかを制御するサーバーがあります。 詳細については、「[Skype for Business Server での Microsoft Teams Rooms を展開する](with-skype-for-business-server-2015.md)」をご覧ください。
    
- ハイブリッド展開: 組織に、オンプレミスでホストされるサービスと、Microsoft 365 または Office 365 を介してオンラインでホストされるサービスが混在しています。 Microsoft Teams Rooms では、次のハイブリッド シナリオがサポートされています。
    
  - Exchange Online とオンプレミスの Skype for Business Server。
    
  - Microsoft Teamsを使用してオンプレミスにExchangeします。
    
どの構成かによって、デバイス セットアップの準備の方法が変わります。
  
Microsoft Teams Rooms Active Directory、Exchange、および (必要に応じて) Skype for Businessに "リソース アカウント" が必要です。 このアカウントは、会議予定表にアクセスし、Microsoft TeamsやSkype for Business接続を確立するために使用されます。 このアカウントを使用して会議をスケジュールすることで、ユーザーはこのアカウントを予約することができます。 Microsoft Teams Rooms はその会議に参加して、会議の出席者にさまざまな機能を提供することができます。
  
> [!IMPORTANT]
> リソース アカウントがないと、これらの機能は機能しません。
  
すべてのリソース アカウントは、1 つのMicrosoft Teams Rooms インストールに固有です。
  
- リソース アカウントが正しく構成されている必要があります。
    
- リソース アカウントを検証し、適切なMicrosoft サービスに到達できるようにMicrosoft Teams Roomsインフラストラクチャを構成する必要があります。

> [!NOTE] 
> Microsoft Teams パネルを使用している場合、Teams Rooms リソース アカウントは、Teams Rooms パネルと関連付けられたTeams パネルの両方にサインインします。
    
> [!IMPORTANT]
> ハードウェアを実際に設置するよりも十分に前もってアカウントを作成しておくことを、強くお勧めします。 設置の 2 週間から 3 週間前にアカウントの準備を開始するのが理想的です。
> 
Skype for Businessを使用していないハイブリッド環境では、Azure Active Directoryでネイティブにアカウントを作成することを強くお勧めします。 オンプレミスの Active Directoryを使用してアカウントを作成する必要がある場合は、Microsoft Teams Rooms認証が必要であるため、Azure Active Directory (AAD) Connect同期でパスワード同期を有効にする必要があります認証をMicrosoft 365またはOffice 365します。 アカウントを設定するときは、アカウントの電子メール アドレスが、AADのユーザー プリンシパル名 (UPN) と一致していることを確認します。 
  
リソース アカウントは、会議室または共有スペースの名前として認識されるアカウントと考えることができます。 そのスペースを使用して会議をスケジュールする場合は、その会議にリソース アカウントを招待します。
  
Microsoft Teams Roomsをインストールする領域にExchangeリソース メールボックス アカウントが既に設定されている場合は、そのアカウントを Teams Rooms リソース アカウントに変更できます。 完了したら、そのアカウントでMicrosoft Teams Roomsにサインインするだけです。
  
## <a name="basic-configuration"></a>基本構成

これらのプロパティは、Microsoft Teams Roomsを操作するリソース アカウントの最小構成を表します。 リソース アカウントには、さらにセットアップが必要な場合があります。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|Exchange メールボックス (Exchange 2013 SP1 以降、または Exchange Online)  <br/> |Exchangeメールボックスは、リソース アカウントに、メールと会議出席依頼を送受信し、Microsoft Teams Roomsに会議予定表を表示する機能を提供します。 Microsoft Teams Rooms メールボックスは、"room" 型のリソース メールボックスである必要があります。  <br/> |
|Skype for Business が有効  <br/> |Skype for Businessは、ビデオ通話、IM、画面共有など、さまざまなSkype for Business会議機能を使用するために有効にすることができます。  <br/> |
|Password が有効  <br/> |リソース アカウントはパスワードで有効にする必要があります。または、Microsoft Teams、Exchange、またはSkype for Business Serverで認証できません。 すべてのTeams Roomsリソース アカウントでパスワードの有効期限を無効にする必要があります。   <br/> |
   
## <a name="advanced-configuration"></a>詳細構成

基本構成のプロパティを使用すると、単純な環境でリソース アカウントを設定できますが、リソース アカウントを正常に使用するには、Microsoft Teams Roomsが満たす必要があるアカウントに対する他の制限が環境に存在する可能性があります。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|証明書ベースの認証  <br/> |Exchange と Skype for Business Server の両方で証明書が必要になる場合があります。 証明書を展開するには、管理者としてログインするときに証明書を読み込むことができます。  <br/> |

## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms のコンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
