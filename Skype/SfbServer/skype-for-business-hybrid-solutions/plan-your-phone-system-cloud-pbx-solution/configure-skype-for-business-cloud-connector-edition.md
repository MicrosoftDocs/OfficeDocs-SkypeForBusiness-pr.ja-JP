---
title: Skype for Business Cloud Connector エディションを構成および管理する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Skype for business Cloud Connector エディションを構成する方法について説明します。これには、オンプレミスの音声インフラストラクチャと、Skype for Business Online の Office 365 (クラウド PBX) の電話システムとの統合を可能にするための最小限のオンプレミスのトポロジがあります。
ms.openlocfilehash: aa0d8fb37dcaddaca3835b25b94eba6a18e03636
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779163"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a>Skype for Business Cloud Connector エディションを構成および管理する
 
Skype for business Cloud Connector エディションを構成する方法について説明します。これには、オンプレミスの音声インフラストラクチャと、Skype for Business Online の Office 365 (クラウド PBX) の電話システムとの統合を可能にするための最小限のオンプレミスのトポロジがあります。 
  
開始する前に、「 [Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)」の前提条件を確認してください。
  
> [!IMPORTANT]
> このトピックの手順は、Cloud Connector エディション1.4.1 以降にのみ適用されます。 まだ Cloud Connector Edition 2.1 にアップグレードしていない場合は、「 [Cloud connector の新しいバージョンへのアップグレード](upgrade-to-a-new-version-of-cloud-connector.md)」を参照してください。 インストールファイルはから[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)ダウンロードできます。 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a>Skype for Business Cloud Connector エディションを構成する手順

次の表に、Cloud Connector エディションをインストールして構成するために必要な手順を示します。
  
|**手順**|**説明**|
|:-----|:-----|
|[Cloud Connector アプライアンスの準備](prepare-your-cloud-connector-appliance.md) <br/> |インストールファイルをダウンロードし、証明書を準備し、Hyper-v を構成して、クラウドコネクタ展開用に環境を準備します。  <br/> |
|[Cloud Connector で単一のサイトを展開する](deploy-a-single-site-in-cloud-connector.md) <br/> |Cloud Connector の展開にサイトを作成します。  <br/> |
|[Cloud Connector で複数のサイトを展開する](deploy-multiple-sites-in-cloud-connector.md) <br/> |展開にサイトを追加し、単一展開とマルチサイト展開の違いについて説明します。  <br/> |
|[Office 365 組織とのクラウドコネクタ統合を構成する](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |DNS レコードを追加し、ハイブリッドを構成し、PSTN ゲートウェイを設定し、Office 365 ボイスメールの電話システムに対してユーザーを有効にします。  <br/> |
|[Cloud Connector の展開を検証する](validate-your-cloud-connector-deployment.md) <br/> |展開が正しく動作していることを確認してください。  <br/> |
|[Cloud Connector の新しいバージョンにアップグレードする](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |既存の Cloud Connector の展開をバージョン2.1 にアップグレードします。  <br/> |
|[既存の Cloud Connector の展開の構成を変更する](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |既に展開されている場合、Cloud Connector の設定を変更します。  <br/> |
|[Cloud Connector エディションでのメディアバイパスの展開](deploy-media-bypass-in-cloud-connector.md) <br/> |Cloud Connector でメディアバイパスを展開する方法について説明します。  <br/> |
|[Cloud Connector コマンドレットリファレンス](cloud-connector-cmdlet-reference.md) <br/> |Cloud Connector で使用される PowerShell コマンドレットについて説明します。  <br/> |
|[Cloud Connector の展開のトラブルシューティング](troubleshoot-your-cloud-connector-deployment.md) <br/> |Cloud Connector の展開で発生する一般的な問題の解決方法を示します。  <br/> |
   

