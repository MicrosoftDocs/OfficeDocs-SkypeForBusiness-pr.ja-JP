---
title: Skype for Business Cloud Connector Edition の構成と管理
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
description: Skype for Business Cloud Connector Edition (最小限のオンプレミス トポロジ) を構成して、Skype for Business Online でオンプレミスの音声インフラストラクチャと電話システム (Cloud PBX) 音声サービスを統合する方法について学習します。
ms.openlocfilehash: 4d24e5a312275158f276856aa78396ad63dff615
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094875"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a>Skype for Business Cloud Connector Edition の構成と管理
 
> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

Skype for Business Cloud Connector Edition (最小限のオンプレミス トポロジ) を構成して、Skype for Business Online でオンプレミスの音声インフラストラクチャと電話システム (Cloud PBX) 音声サービスを統合する方法について学習します。 
  
開始する前に [、「Plan for Skype for Business Cloud Connector Edition」の前提条件を確認する必要があります](plan-skype-for-business-cloud-connector-edition.md)。
  
> [!IMPORTANT]
> このトピックの手順は、Cloud Connector Edition 1.4.1 以降にのみ適用されます。 まだ Cloud Connector Edition 2.1 にアップグレードしていない場合は、「新しいバージョンのクラウド コネクタにアップグレードする」 [を参照してください](upgrade-to-a-new-version-of-cloud-connector.md)。 インストール ファイルは、 からダウンロードできます [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a>Skype for Business Cloud Connector Edition を構成する手順

次の表に、Cloud Connector Edition をインストールして構成する必要がある手順を示します。
  
|**手順**|**説明**|
|:-----|:-----|
|[Cloud Connector アプライアンスの準備](prepare-your-cloud-connector-appliance.md) <br/> |インストール ファイルをダウンロードし、証明書を準備し、Hyper-V を構成し、クラウド コネクタの展開に備える環境を取得します。  <br/> |
|[Cloud Connector での単一サイトの展開](deploy-a-single-site-in-cloud-connector.md) <br/> |クラウド コネクタ展開でサイトを作成します。  <br/> |
|[Cloud Connector での複数サイトの展開](deploy-multiple-sites-in-cloud-connector.md) <br/> |展開にサイトを追加し、単一サイト展開と複数サイト展開の違いについて説明します。  <br/> |
|[Microsoft 365 または 365 組織とのクラウド コネクタOffice構成する](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |DNS レコードの追加、ハイブリッドの構成、PSTN ゲートウェイのセットアップ、および電話システムボイス メールのユーザーの有効化。  <br/> |
|[Cloud Connector 展開の検証](validate-your-cloud-connector-deployment.md) <br/> |展開が正しく動作するようにします。  <br/> |
|[Cloud Connector 新バージョンへのアップグレード](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |既存のクラウド コネクタ展開をバージョン 2.1 にアップグレードします。  <br/> |
|[既存の Cloud Connector の展開構成の変更](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |クラウド コネクタが既に展開された後で、クラウド コネクタの設定を変更します。  <br/> |
|[Cloud Connector Edition でのメディア バイパスの展開](deploy-media-bypass-in-cloud-connector.md) <br/> |クラウド コネクタでメディア バイパスを展開する方法について学習します。  <br/> |
|[Cloud Connector コマンドレットのリファレンス](cloud-connector-cmdlet-reference.md) <br/> |クラウド コネクタで使用される PowerShell コマンドレットについて説明します。  <br/> |
|[Cloud Connector 展開のトラブルシューティング](troubleshoot-your-cloud-connector-deployment.md) <br/> |クラウド コネクタの展開で発生する一般的な問題に対する解決策。  <br/> |
