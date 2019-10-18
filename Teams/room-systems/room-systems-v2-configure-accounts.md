---
title: Microsoft Teams 室のアカウントを構成する
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: このトピックでは、Exchange および Skype for Business で Microsoft Teams ルームのアカウントを構成する方法について説明します。
ms.openlocfilehash: 287ebcd421a41f088774920a2ec655ac7c562038
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573618"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Microsoft Teams 室のアカウントを構成する
 
このトピックでは、Microsoft Teams のルームの概要と Exchange と Skype for Business との統合について説明します。
  
このトピックでは、microsoft Teams のルームで使用されるアカウントを Microsoft Exchange および Skype for Business で作成する方法について説明します。 Microsoft Teams の会議室デバイスの展開手順については[、「Microsoft Teams 室コンソールを構成する](console.md)」をご利用ください。 通常、インフラストラクチャは次のいずれかの構成に該当します。
  
- オンライン展開: 組織の環境は、完全に Office 365 に展開されます。 詳細については、「 [Office 365 で Microsoft Teams ルームを展開](with-office-365.md)する」を参照してください。
    
- オンプレミスの展開: 組織には、Active Directory、Exchange、および Skype for Business Server がホストされていることを制御するサーバーがあります。 詳細については、「 [Skype For Business Server で Microsoft Teams のルームを展開](with-skype-for-business-server-2015.md)する」を参照してください。
    
- ハイブリッド展開: 組織には、オンプレミスのホストと、Office 365 を介してオンラインでホストされているサービスが混在しています。 Microsoft Teams のルームでは、次のハイブリッドシナリオがサポートされています。 
    
  - オンプレミスの Skype for Business Server での Exchange Online。 詳細については、「 [Microsoft Teams のルームを Exchange Online (ハイブリッド) と連携](with-exchange-online.md)させる」を参照してください。
    
  - Microsoft Teams または Skype for Business Online でオンプレミスの Exchange に接続します。 詳細については、「 [Exchange on プレミス (ハイブリッド) で Microsoft Teams のルームを展開](with-exchange-on-premises.md)する」を参照してください。
    
使用する構成は、デバイスのセットアップの準備方法に影響します。
  
Microsoft Teams の会議室には、Active Directory、Exchange、Skype for Business に "デバイスアカウント" が割り当てられている必要があります。 アカウントは、会議の予定表にアクセスし、Microsoft Teams または Skype for Business の接続を確立するために使用されます。 ユーザーは、このアカウントで会議をスケジュール設定することで、このアカウントを予約できます。 Microsoft Teams のルームは、会議に参加し、会議の出席者にさまざまな機能を提供することができます。
  
> [!IMPORTANT]
> デバイスアカウントがない場合は、これらの機能は使用できません。 
  
すべてのデバイスアカウントは、1つの Microsoft Teams のルームデバイスに固有のものであり、いくつかのセットアップが必要です。
  
- デバイスアカウントが正しく構成されている必要があります。
    
- Microsoft Teams の会議でデバイスアカウントを検証し、適切な Microsoft サービスにアクセスできるように、インフラストラクチャを構成する必要があります。
    
> [!IMPORTANT]
> ハードウェアを実際に設置するよりも十分に前もってアカウントを作成しておくことを、強くお勧めします。 設置の 2 週間から 3 週間前にアカウントの準備を開始するのが理想的です。 ハイブリッド環境では、microsoft Teams 会議室で使用されるアカウントでは、Microsoft Teams の会議室認証に Office 365 認証が必要であるため、AAD の同期でパスワード同期が有効になっている必要があります。
  
デバイスアカウントは、会議室または会議スペースのアカウントとして認識されるリソースアカウントと考えることができます。 こうした会議室を使用する会議を予約する場合は、そのアカウントを会議に招待します。 Microsoft Teams の会議室を最も効果的に使用するために、各ユーザーに割り当てられているデバイスアカウントと同じ操作を行います。
  
Microsoft Teams のルームをインストールしている会議スペースにリソースメールボックスアカウントが既に設定されている場合は、そのリソースアカウントをデバイスアカウントに変更することができます。 この作業が完了したら、デバイスアカウントを Microsoft Teams 室のデバイスに追加するだけです。 以下の「デバイスアカウントのセットアップ例」を参照してください。
  
追加の構成では、「 [Microsoft teams のルーム管理を Azure monitor で計画](azure-monitor-plan.md)する」、「 [Microsoft teams のルーム管理を azure monitor で展開](azure-monitor-deploy.md)する」の説明に従って、microsoft azure モニターを使用してリモート管理を行う[ことができます。Azure モニターを使用して、Microsoft Teams のルームデバイスを管理](azure-monitor-manage.md)します。 
  
## <a name="basic-configuration"></a>基本構成

これらのプロパティは、Microsoft Teams のルームで動作するデバイスアカウントの最小構成を表します。 デバイスアカウントに追加のセットアップが必要な場合があります。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|Exchange メールボックス (Exchange 2013 SP1 以降、または Exchange Online)  <br/> |Exchange メールボックスを使用してアカウントを有効にすると、デバイスアカウントは、メールおよび会議の出席依頼の受信と送信を行うことができます。また、Microsoft Teams のルームデバイスで会議の予定表を表示することもできます。 Microsoft Teams 会議のメールボックスは、会議室メールボックスである必要があります。  <br/> |
|Skype for Business が有効になっています  <br/> |Skype for Business は、ビデオ通話、IM、画面共有などのさまざまな会議機能を使用するために有効にする必要があります。 Skype for Business Online と Skype for business Server の両方がサポートされています。  <br/> |
|パスワードが有効になっている  <br/> |デバイスアカウントは、パスワードを使用して有効にする必要があります。または、Exchange または Skype for Business Server で認証することはできません。  <br/> |
   
## <a name="advanced-configuration"></a>詳細構成

基本構成のプロパティによってデバイスアカウントを簡単な環境で設定することはできますが、Microsoft Teams のルームで正常に使用できるようにするために満たす必要があるディレクトリアカウントについては、環境にその他の制限がある可能性があります。デバイスアカウント。
  
|**プロパティ**|**用途**|
|:-----|:-----|
|証明書ベースの認証  <br/> |Exchange と Skype for Business Server の両方で証明書が必要になることがあります。 証明書を展開するには、管理者としてログインしたときに証明書をロードできます。  <br/> |
   
デバイスアカウントを設定する最も簡単な方法は、リモートの Windows PowerShell を使って構成することです。 Microsoft は[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105)を提供します。これは、新しいデバイスアカウントを作成するのに役立ちます。また、既存のリソースアカウントを、互換性のある Microsoft Teams のルームデバイスアカウントに変換するために使用されます。
  
Windows PowerShell コマンドレットで Office 365 UI を使用する場合は、いくつかの手順を手動で実行できます。 「 [Office 365 を使ってデバイスアカウントを作成](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)する」を参照してください。
  
## <a name="see-also"></a>関連項目

[Microsoft Teams のルームを計画する](skype-room-systems-v2-0.md)
  
[Microsoft Teams 室コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)

