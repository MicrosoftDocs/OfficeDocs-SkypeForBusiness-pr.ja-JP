---
title: パイロット エッジ サーバーを展開する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: このトピックでは、Skype for Business Server 2019 エッジサーバーを展開する前に認識しておく必要がある構成設定について説明します。 Skype for Business Server 2019 の展開および構成プロセスは、Skype for business Server 2015 によく似ています。 このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。 詳細な手順については、「展開」のドキュメントの「Deployment external user access in Skype for Business Server 2019」 (展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供します) を参照してください。
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752869"
---
# <a name="deploy-pilot-edge-server"></a>パイロット エッジ サーバーを展開する

このトピックでは、Skype for Business Server 2019 エッジサーバーを展開する前に知っておく必要がある構成設定について説明します。 Skype for Business Server 2019 の展開および構成プロセスは、Skype for business Server 2015 によく似ています。 このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。 <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown. 
  
### <a name="to-define-an-edge-pool"></a>エッジプールを定義するには

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. [Skype for Business Server 2019 ノードに移動します。 [**エッジ プール**] を右クリックし、[**新しいエッジ プール**] をクリックします。
    
     ![[新しいエッジプールの定義] ダイアログボックス](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. エッジ プールは、[**複数のコンピューター プール**] または [**単一コンピューター プール**] のどちらかになります。
    
     ![[エッジプールの FQDN の定義] ダイアログボックス](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. [**機能の選択**] ページでは、フェデレーションまたは XMPP フェデレーションを有効にしないでください。 フェデレーションと XMPP フェデレーションは、現在、従来のエッジサーバーを経由してルーティングされます。 この機能は、後ほど移行のフェーズで構成されます。 

  
5. 引き続き、[**外部 fqdn**]、[**内部 ip アドレスの定義**]、および [**外部 ip アドレスの定義**] の各ウィザードページを完了します。
    
6. [**次ホップサーバーの定義**] ページで、従来のエッジプールの次ホップのディレクターを選択します。 
    
     ![[次ホップの定義] ダイアログボックス](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. [**フロントエンドまたは仲介プールの関連付け**] ページで、現時点ではプールをこのエッジプールに関連付けないでください。 外部メディアトラフィックは、現在、従来のエッジサーバーを経由してルーティングされています。 この設定は、後ほど移行のフェーズで構成されます。 
    
     ![[フロントエンドプールの関連付け] ダイアログボックス](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. [**完了**] をクリックしてトポロジを**公開**します。 
    
9. 「展開」のドキュメントの手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
「展開」のドキュメントのトピックのガイドラインに従うことが非常に重要です。 このセクションでは、これらのサーバーの役割をインストールする際の構成設定に関するガイドラインの一部を提供したにすぎません。 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
これで、Skype for Business Server 2019 エッジサーバー展開と並行して展開された従来のエッジサーバーを使用できるようになります。 次のフェーズに進む前に、双方の展開が適切に動作していること、サービスが開始されていること、および各展開を管理できることを確認してください。 
  

