---
title: パイロット エッジ サーバーの展開
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: このトピックでは、2019 エッジ サーバーを展開する前に注意する必要がある構成Skype for Business Server説明します。 2019 年 2019 年Skype for Business Server展開および構成プロセスは、2015 年の Skype for Business Serverと非常に似ています。 このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。 詳細な手順については、「展開プロセスについて説明し、外部ユーザー アクセスの構成情報も示す展開」の「Skype for Business Server 2019 での外部ユーザー アクセスの展開」を参照してください。
ms.openlocfilehash: c76d517bd5130c2babc41e0072ae7450b9838a64
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615011"
---
# <a name="deploy-pilot-edge-server"></a>パイロット エッジ サーバーの展開

このトピックでは、2019 エッジ サーバーを展開する前に注意する必要がある構成Skype for Business Server説明します。 2019 年 2019 年Skype for Business Server展開および構成プロセスは、2015 年の Skype for Business Serverと非常に似ています。 このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。 <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
**新しいエッジ プールの定義** ウィザードでは、以下の手順に示すキー構成の設定を確認してください。ただし、**新しいエッジ プールの定義** ウィザードのごく一部のページのみが示されています。 
  
### <a name="to-define-an-edge-pool"></a>エッジ プールを定義するには

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. 2019 Skype for Business Serverに移動します。 [**エッジ プール**] を右クリックし、[**新しいエッジ プール**] をクリックします。
    
     ![[新しいエッジ プールの定義] ダイアログ ボックス](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. エッジ プールは、[**複数のコンピューター プール**] または [**単一コンピューター プール**] のどちらかになります。
    
     ![[エッジ プールの FQDN の定義] ダイアログ ボックス](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. [**機能の選択**] ページでは、フェデレーションまたは XMPP フェデレーションを有効にしないでください。 フェデレーションと XMPP フェデレーションはどちらも、現在レガシ エッジ サーバー経由でルーティングされています。 この機能は、後ほど移行のフェーズで構成されます。 

  
5. 次のウィザード ページの完了を続行します。外部 **FQDN、****内部 IP** アドレスの定義、および外部 IP アドレス **の定義**。
    
6. [次ホップ **サーバーの定義] ページ** で、レガシ エッジ プールの次ホップのディレクターを選択します。 
    
     ![[次ホップの定義] ダイアログ ボックス](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. [フロントエンド プール **または仲介プールの関連付け** ] ページで、現時点ではプールをこのエッジ プールに関連付けは行わなきます。 外部メディア トラフィックは現在、従来のエッジ サーバーを経由してルーティングされます。 この設定は、後ほど移行のフェーズで構成されます。 
    
     ![[フロントエンド プールの関連付け] ダイアログ ボックス](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. [**完了**] をクリックしてトポロジを **公開** します。 
    
9. 展開のドキュメントの手順に従って、新しいエッジ サーバーにファイルをインストールし、証明書を構成し、サービスを開始します。 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
展開に関するドキュメントのトピックのガイドラインに従う必要があります。 このセクションでは、これらのサーバーの役割をインストールする際の構成設定に関するガイドラインの一部を提供したにすぎません。 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
従来のエッジ サーバーを 2019 エッジ サーバーの展開と並行して展開Skype for Business Server必要があります。 次のフェーズに進む前に、双方の展開が適切に動作していること、サービスが開始されていること、および各展開を管理できることを確認してください。 
  

