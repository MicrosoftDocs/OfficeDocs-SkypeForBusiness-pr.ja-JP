---
title: Microsoft Teams Rooms のアカウントを構成する
ms.author: dstrome
author: dstrome
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
description: このトピックでは、Exchange と Skype for Business で Microsoft Teams Rooms のアカウントを構成する方法について説明します。
ms.openlocfilehash: 77e1dbe097bbb75697ec52ef7d472df4707ac9cb
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306122"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Microsoft Teams Rooms のアカウントを構成する
 
このトピックでは、Microsoft Teams Rooms の概要と、Exchange や Skype for Business との統合方法について説明します。
  
このトピックでは、Microsoft Exchange や Skype for Business で Microsoft Teams Rooms に使用されるアカウントを作成する方法について説明します。 インフラストラクチャは、次のいずれかの構成に分類されます。
  
- オンライン展開: 組織の環境全体が Microsoft 365 または Office 365 に展開されます。 詳細については、「[Microsoft 365 または Office 365 で Microsoft Teams Rooms を展開する](with-office-365.md)」をご覧ください。
    
- オンプレミス展開: 組織に、Active Directory、Exchange、Skype for Business Server がどこでホストされるかを制御するサーバーがあります。 詳細については、「[Skype for Business Server での Microsoft Teams Rooms を展開する](with-skype-for-business-server-2015.md)」をご覧ください。
    
- ハイブリッド展開: 組織に、オンプレミスでホストされるサービスと、Microsoft 365 または Office 365 を介してオンラインでホストされるサービスが混在しています。 Microsoft Teams Rooms では、次のハイブリッド シナリオがサポートされています。
    
  - Exchange Online とオンプレミスの Skype for Business Server。 詳細については、「[Exchange Online を使用して Microsoft Teams Rooms を展開 (ハイブリッド)](with-exchange-online.md)」をご覧ください。
    
  - Exchangeを使用してオンプレミスにMicrosoft Teams。 詳細については、「[オンプレミスで Exchange を使用して Microsoft Teams Rooms を展開 (ハイブリッド)](with-exchange-on-premises.md)」をご覧ください。
    
どの構成かによって、デバイス セットアップの準備の方法が変わります。
  
Microsoft Teams、Active Directory、Exchange、およびリソース アカウントに "リソース アカウント" が割り当てられているSkype for Business。 このアカウントは、会議の予定表にアクセスし、Microsoft Teams または Skype for Business の接続を確立するために使用されます。 このアカウントを使用して会議をスケジュールすることで、ユーザーはこのアカウントを予約することができます。 Microsoft Teams Rooms はその会議に参加して、会議の出席者にさまざまな機能を提供することができます。
  
> [!IMPORTANT]
> リソース アカウントがない場合、これらの機能はいずれも機能しません。 
  
すべてのリソース アカウントは、会議室のインストールMicrosoft Teams一意であり、いくつかのセットアップが必要です。
  
- リソース アカウントが正しく構成されている必要があります。
    
- お客様のインフラストラクチャは、Microsoft Teams アカウントを検証し、適切なリソース アカウントに到達Microsoft サービス。

> [!NOTE] 
> パネルをMicrosoft Teams場合、Teams Rooms リソース アカウントは、Teams Rooms と関連付けられている Teamsにサインインします。
    
> [!IMPORTANT]
> ハードウェアを実際に設置するよりも十分に前もってアカウントを作成しておくことを、強くお勧めします。 設置の 2 週間から 3 週間前にアカウントの準備を開始するのが理想的です。
> 

Microsoft Teams Rooms で使用されるアカウントは、Azure Active Directory (AAD) Sync でパスワード同期を有効にする必要があります。Microsoft Teams Rooms 認証にはパスワードまたはパスワードがMicrosoft 365必要Office 365認証。 アカウントを設定するときに、アカウントの SIP アドレスが、アカウント内のユーザー プリンシパル名 (UPN) と一致AAD。 
  
リソース アカウントは、ユーザーが会議室または共有スペースのアカウントとして認識するリソース アカウントと考える場合があります。 そのスペースを使用して会議をスケジュールする場合は、その会議にアカウントを招待します。
  
Microsoft Teams 会議室をインストールする領域にリソース メールボックス アカウントが既に設定されている場合は、そのアカウントを Teams Rooms リソース アカウントに変更できます。 完了したら、そのアカウントで Microsoft Teams にサインインする必要があります。
  
## <a name="basic-configuration"></a>基本構成

これらのプロパティは、リソース アカウントが会議室で動作する最小構成Microsoft Teamsします。 リソース アカウントには、さらにセットアップが必要な場合があります。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|Exchange メールボックス (Exchange 2013 SP1 以降、または Exchange Online)  <br/> |Exchange メールボックスを使用してアカウントを有効にすると、リソース アカウントは、メールと会議出席依頼の両方を送受信し、Microsoft Teams Rooms デバイスに会議予定表を表示できます。 Microsoft Teams Rooms のメールボックスは、会議室メールボックスである必要があります。  <br/> |
|Skype for Business が有効  <br/> |Skype for Business、IM、画面共有など、さまざまな会議Skype for Business機能を使用するために、この機能を有効にできます。  <br/> |
|Password が有効  <br/> |リソース アカウントは、パスワードで有効にする必要があります。または、Microsoft Teams、Exchange、またはSkype for Business Server。 パスワードの有効期限は、会議室のすべてのリソース アカウントTeams無効にする必要があります。   <br/> |
   
## <a name="advanced-configuration"></a>詳細構成

基本構成のプロパティを使用すると、単純な環境でリソース アカウントを設定することができますが、Microsoft Teams Rooms がリソース アカウントを正常に使用するために必要なディレクトリ アカウントに対して、環境に他の制限が適用されている可能性があります。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|証明書ベースの認証  <br/> |Exchange と Skype for Business Server の両方で証明書が必要になる場合があります。 証明書を展開するには、管理者としてログインするときに証明書を読み込むことができます。  <br/> |
  
## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms のコンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
