---
title: サーバーの構成とSkype for Business クラウド コネクタ エディション
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
description: Skype for Business クラウド コネクタ エディション Online の 電話システム (Cloud PBX) 音声サービスとのオンプレミス音声インフラストラクチャの統合を可能にする最小限のオンプレミス トポロジである Skype for Business クラウド コネクタ エディション を構成する方法についてSkype for Businessします。
ms.openlocfilehash: 23502d95ad1c6b0282dfb5cd074c48560b11717175befe8bc460bb73523ab69f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349619"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a>サーバーの構成とSkype for Business クラウド コネクタ エディション
 
> [!Important]
> Cloud Connector Edition は、2021 年 7 月 31 日にオンライン版と共Skype for Business廃止されます。 組織がネットワーク にアップグレードしたらTeamsルーティングを使用してオンプレミスのテレフォニー ネットワークをネットワークに接続するTeams[説明します](/MicrosoftTeams/direct-routing-landing-page)。

Skype for Business クラウド コネクタ エディション Online の 電話システム (Cloud PBX) 音声サービスとのオンプレミス音声インフラストラクチャの統合を可能にする最小限のオンプレミス トポロジである Skype for Business クラウド コネクタ エディション を構成する方法についてSkype for Businessします。 
  
開始する前に、「プラン for Skype for Business クラウド コネクタ エディション」[で前提条件を確認する必要があります](plan-skype-for-business-cloud-connector-edition.md)。
  
> [!IMPORTANT]
> このトピックの手順は、Cloud Connector Edition 1.4.1 以降にのみ適用されます。 まだ Cloud Connector Edition 2.1 にアップグレードしていない場合は、「新しいバージョンのクラウド コネクタにアップグレードする」 [を参照してください](upgrade-to-a-new-version-of-cloud-connector.md)。 インストール ファイルは、 からダウンロードできます [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a>デバイスを構成するSkype for Business クラウド コネクタ エディション

次の表に、Cloud Connector Edition をインストールして構成する必要がある手順を示します。
  
|**手順**|**説明**|
|:-----|:-----|
|[Cloud Connector アプライアンスの準備](prepare-your-cloud-connector-appliance.md) <br/> |インストール ファイルをダウンロードし、証明書を準備し、Hyper-V を構成し、クラウド コネクタの展開に備える環境を取得します。  <br/> |
|[Cloud Connector での単一サイトの展開](deploy-a-single-site-in-cloud-connector.md) <br/> |クラウド コネクタ展開でサイトを作成します。  <br/> |
|[Cloud Connector での複数サイトの展開](deploy-multiple-sites-in-cloud-connector.md) <br/> |展開にサイトを追加し、単一サイト展開と複数サイト展開の違いについて説明します。  <br/> |
|[クラウド コネクタの統合を組織または組織Microsoft 365構成Office 365する](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |DNS レコードの追加、ハイブリッドの構成、PSTN ゲートウェイのセットアップ、およびボイス 電話システム有効にします。  <br/> |
|[Cloud Connector 展開の検証](validate-your-cloud-connector-deployment.md) <br/> |展開が正しく動作するようにします。  <br/> |
|[Cloud Connector 新バージョンへのアップグレード](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |既存のクラウド コネクタ展開をバージョン 2.1 にアップグレードします。  <br/> |
|[既存の Cloud Connector の展開構成の変更](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |クラウド コネクタが既に展開された後で、クラウド コネクタの設定を変更します。  <br/> |
|[Cloud Connector Edition でのメディア バイパスの展開](deploy-media-bypass-in-cloud-connector.md) <br/> |クラウド コネクタでメディア バイパスを展開する方法について学習します。  <br/> |
|[Cloud Connector コマンドレットのリファレンス](cloud-connector-cmdlet-reference.md) <br/> |クラウド コネクタで使用される PowerShell コマンドレットについて説明します。  <br/> |
|[Cloud Connector 展開のトラブルシューティング](troubleshoot-your-cloud-connector-deployment.md) <br/> |クラウド コネクタの展開で発生する一般的な問題に対する解決策。  <br/> |
