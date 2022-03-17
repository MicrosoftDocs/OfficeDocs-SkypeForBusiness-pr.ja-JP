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
description: このトピックでは、会議室 (Microsoft Teams を含む) と一般的なエリアSurface Hubアカウントを構成する方法について説明します。
ms.openlocfilehash: 4ecac71ef862fda003523bbcefe3c333daefaa23
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514732"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Microsoft Teams Rooms のアカウントを構成する
 
このトピックでは、会議室で使用されるアカウントを作成するMicrosoft Teamsします。 インフラストラクチャは、次のいずれかの構成に分類されます。
  
- オンライン展開: 組織の環境全体が Microsoft 365 または Office 365 に展開されます。
    
- オンプレミス展開: 組織に、Active Directory、Exchange、Skype for Business Server がどこでホストされるかを制御するサーバーがあります。 詳細については、「[Skype for Business Server での Microsoft Teams Rooms を展開する](with-skype-for-business-server-2015.md)」をご覧ください。
    
- ハイブリッド展開: 組織に、オンプレミスでホストされるサービスと、Microsoft 365 または Office 365 を介してオンラインでホストされるサービスが混在しています。 Microsoft Teams Rooms では、次のハイブリッド シナリオがサポートされています。
    
  - Exchange Online とオンプレミスの Skype for Business Server。
    
  - Exchangeを使用してオンプレミスMicrosoft Teams。
    
どの構成かによって、デバイス セットアップの準備の方法が変わります。
  
Microsoft Teams、Active Directory、Exchange、および (必要に応じて) [リソース アカウント] がSkype for Business。 このアカウントは、会議の予定表にアクセスし、会議のMicrosoft Teams接続を確立Skype for Business使用されます。 このアカウントを使用して会議をスケジュールすることで、ユーザーはこのアカウントを予約することができます。 Microsoft Teams Rooms はその会議に参加して、会議の出席者にさまざまな機能を提供することができます。
  
> [!IMPORTANT]
> リソース アカウントがない場合、これらの機能はいずれも機能しません。
  
すべてのリソース アカウントは、会議室のインストールMicrosoft Teams一意です。
  
- リソース アカウントが正しく構成されている必要があります。
    
- お客様のインフラストラクチャは、Microsoft Teams Rooms がリソース アカウントを検証し、適切なリソース アカウントに到達Microsoft サービス。

> [!NOTE] 
> パネルをMicrosoft Teams場合、Teams Rooms リソース アカウントは、Teams Rooms と関連付けられている Teamsにサインインします。
    
> [!IMPORTANT]
> ハードウェアを実際に設置するよりも十分に前もってアカウントを作成しておくことを、強くお勧めします。 設置の 2 週間から 3 週間前にアカウントの準備を開始するのが理想的です。
> 
アプリケーションを使用していないハイブリッド環境Skype for Business、アカウントをアプリケーションでネイティブに作成することを強Azure Active Directory。 オンプレミスの Active Directory を使用してアカウントを作成する必要が生じ、Microsoft Teams Rooms 認証でパスワード同期が必要Azure Active Directory (AAD) Connect 同期でパスワード同期を有効にする必要Microsoft 365またはOffice 365認証。 アカウントを設定するときに、アカウントの電子メール アドレスが、アカウント内のユーザー プリンシパル名 (UPN) と一致AAD。 
  
リソース アカウントは、ユーザーが会議室または共有スペースの名前として認識するアカウントと考える場合があります。 そのスペースを使用して会議をスケジュールする場合は、その会議にリソース アカウントを招待します。
  
Microsoft Teams 会議室をインストールする領域に Exchange リソース メールボックス アカウントが既に設定されている場合は、そのアカウントを Teams Rooms リソース アカウントに変更できます。 この操作が完了したら、そのアカウントで Microsoft Teams にサインインする必要があります。
  
## <a name="basic-configuration"></a>基本構成

これらのプロパティは、リソース アカウントが会議室で動作する最小構成Microsoft Teamsします。 リソース アカウントには、さらにセットアップが必要な場合があります。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|Exchange メールボックス (Exchange 2013 SP1 以降、または Exchange Online)  <br/> |Exchangeメールボックスでは、リソース アカウントにメールや会議出席依頼を送受信し、会議の予定表を [会議室] に表示Microsoft Teamsします。 会議室Microsoft Teamsは、"会議室" タイプのリソース メールボックスである必要があります。  <br/> |
|Skype for Business が有効  <br/> |Skype for Business、IM、画面共有など、さまざまな会議Skype for Business機能を使用するために、この機能を有効にできます。  <br/> |
|Password が有効  <br/> |リソース アカウントは、パスワードで有効にする必要があります。または、Microsoft Teams、Exchange、または Skype for Business Server で認証することはできません。 パスワードの有効期限は、すべての会議室リソース Teams無効にする必要があります。   <br/> |
   
## <a name="advanced-configuration"></a>詳細構成

基本的な構成のプロパティを使用すると、単純な環境でリソース アカウントを設定することができますが、Microsoft Teams Rooms がリソース アカウントを正常に使用するために必要なアカウントに対して、環境に他の制限が適用されている可能性があります。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|証明書ベースの認証  <br/> |Exchange と Skype for Business Server の両方で証明書が必要になる場合があります。 証明書を展開するには、管理者としてログインするときに証明書を読み込むことができます。  <br/> |

## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms のコンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
