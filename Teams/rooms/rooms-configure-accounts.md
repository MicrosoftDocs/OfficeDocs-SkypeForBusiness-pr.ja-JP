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
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: このトピックでは、Exchange と Skype for Business で Microsoft Teams Rooms のアカウントを構成する方法について説明します。
ms.openlocfilehash: e171ef22dd1733c06b03a4a9483f591d73d70cb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662522"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Microsoft Teams Rooms のアカウントを構成する
 
このトピックでは、Microsoft Teams Rooms の概要と、Exchange や Skype for Business との統合方法について説明します。
  
このトピックでは、Microsoft Exchange や Skype for Business で Microsoft Teams Rooms に使用されるアカウントを作成する方法について説明します。 Microsoft Teams Rooms デバイスの展開手順は、「[Microsoft Teams Rooms のコンソールを構成する](console.md)」で取り上げられてます。 インフラストラクチャは、次のいずれかの構成に分類されます。
  
- オンライン展開: 組織の環境全体が Microsoft 365 または Office 365 に展開されます。 詳細については、「[Microsoft 365 または Office 365 で Microsoft Teams Rooms を展開する](with-office-365.md)」をご覧ください。
    
- オンプレミス展開: 組織に、Active Directory、Exchange、Skype for Business Server がどこでホストされるかを制御するサーバーがあります。 詳細については、「[Skype for Business Server での Microsoft Teams Rooms を展開する](with-skype-for-business-server-2015.md)」をご覧ください。
    
- ハイブリッド展開: 組織に、オンプレミスでホストされるサービスと、Microsoft 365 または Office 365 を介してオンラインでホストされるサービスが混在しています。 Microsoft Teams Rooms では、次のハイブリッド シナリオがサポートされています。
    
  - Exchange Online とオンプレミスの Skype for Business Server。 詳細については、「[Exchange Online を使用して Microsoft Teams Rooms を展開 (ハイブリッド)](with-exchange-online.md)」をご覧ください。
    
  - オンプレミスの Exchange と Microsoft Teams または Skype for Business Online。 詳細については、「[オンプレミスで Exchange を使用して Microsoft Teams Rooms を展開 (ハイブリッド)](with-exchange-on-premises.md)」をご覧ください。
    
どの構成かによって、デバイス セットアップの準備の方法が変わります。
  
Microsoft Teams Rooms には、Active Directory、Exchange、Skype for Business の "デバイス アカウント" が割り当てられている必要があります。 このアカウントは、会議の予定表にアクセスし、Microsoft Teams または Skype for Business の接続を確立するために使用されます。 このアカウントを使用して会議をスケジュールすることで、ユーザーはこのアカウントを予約することができます。 Microsoft Teams Rooms はその会議に参加して、会議の出席者にさまざまな機能を提供することができます。
  
> [!IMPORTANT]
> デバイス アカウントがないと、これらの機能はいずれも動作しません。 
  
それぞれのデバイス アカウントは 1 つの Microsoft Teams Rooms デバイスに固有で、設定が必要です。
  
- デバイス アカウントは正しく構成する必要があります。
    
- Microsoft Teams Rooms がデバイス アカウントを確認し、適切な Microsoft のサービスに到達できるように、インフラストラクチャを構成する必要があります。
    
> [!IMPORTANT]
> ハードウェアを実際に設置するよりも十分に前もってアカウントを作成しておくことを、強くお勧めします。 設置の 2 週間から 3 週間前にアカウントの準備を開始するのが理想的です。 

Microsoft Teams Rooms 認証には Microsoft 365 または Office 365 認証が必要なので、ハイブリッド環境では、Microsoft Teams Rooms で使用されるアカウントで、Azure Active Directory (AAD) 同期でパスワード同期が有効になっている必要があります。 アカウントをセットアップするときに、アカウントの SIP アドレスが AAD のユーザー プリンシパル名 (UPN) と一致する必要があります。 
  
デバイス アカウントは、会議室やミーティング スペースのアカウントとして認識されるリソース アカウントと見なすことができます。 その会議室を使って会議をスケジュールするときは、アカウントをその会議に招待します。 Microsoft Teams Rooms を最も効果的に利用するには、各会議室に割り当てられているデバイス アカウントで同じ操作を行います。
  
Microsoft Teams Rooms をインストールするミーティング スペース用に設定されたリソース メールボックス アカウントが既に存在する場合は、そのリソース アカウントをデバイス アカウントに変更することができます。 その操作が完了した後に行う必要があるのは、デバイス アカウントを Microsoft Teams Rooms デバイスに追加することだけです。 下記のデバイス アカウントのセットアップ例を参照してください。
  
「[Azure Monitor を使用して Microsoft Teams Rooms の管理を計画する](azure-monitor-plan.md)」、「[Azure Monitor を使用して Microsoft Teams Rooms の管理を展開する](azure-monitor-deploy.md)」、「[Azure Monitor を使用して Microsoft Teams Rooms のデバイスを管理する](azure-monitor-manage.md)」で説明されているように、追加の構成を行えば Microsoft Azure Monitor を使用してリモート管理を行うことが可能になります。 
  
## <a name="basic-configuration"></a>基本構成

次のプロパティは、デバイス アカウントが Microsoft Teams Rooms で機能するための最小構成を示しています。 デバイス アカウントによっては、追加のセットアップが必要な場合があります。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|Exchange メールボックス (Exchange 2013 SP1 以降、または Exchange Online)  <br/> |アカウントを Exchange メールボックスで有効にすると、そのデバイス アカウントはメールと会議出席依頼の両方を送受信し、Microsoft Teams Rooms デバイスで会議の予定表を表示できるようになります。 Microsoft Teams Rooms のメールボックスは、会議室メールボックスである必要があります。  <br/> |
|Skype for Business が有効  <br/> |ビデオ通話、IM、画面共有などのさまざまな会議機能を使用するには、Skype for Business が有効である必要があります。 Skype for Business Online と Skype for Business Server の両方がサポートされます。  <br/> |
|Password が有効  <br/> |デバイス アカウントはパスワードによって有効になる必要があります。そうでない場合は、Exchange や Skype for Business Server で認証できません。  <br/> |
   
## <a name="advanced-configuration"></a>詳細構成

基本構成のプロパティではシンプルな環境でデバイス アカウントをセットアップできますが、お使いの環境でディレクトリ アカウントに対するその他の制限が存在し、Microsoft Teams Rooms で正常にデバイス アカウントを使用するためにそれらの制限を満たす必要がある可能性があります。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|証明書ベースの認証  <br/> |Exchange と Skype for Business Server の両方で証明書が必要になる場合があります。 証明書を展開するには、管理者としてログインするときに証明書を読み込むことができます。  <br/> |
   
デバイス アカウントをセットアップする最も簡単な方法は、リモート Windows PowerShell を使用して構成することです。 Microsoft では、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) を提供しています。これは、新しいデバイス アカウントを作成するか、既存のリソース アカウントを検証するスクリプトであり、それらのアカウントを互換性のある Microsoft Teams Rooms のデバイス アカウントに変換する助けとなります。
  
Windows PowerShell コマンドレットよりも Microsoft 365 または Office 365 UI を使用することを望む場合は、一部の手順を手動で実行できます。 「[Microsoft 365 または Office 365 を使用してデバイス アカウントを作成する](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)」を参照してください。
  
## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms のコンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)

