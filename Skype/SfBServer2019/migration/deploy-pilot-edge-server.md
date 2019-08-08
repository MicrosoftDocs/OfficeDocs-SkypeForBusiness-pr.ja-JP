---
title: パイロット エッジ サーバーの展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: このトピックでは、Skype for Business Server 2019 Edge サーバーを展開する前に知っておく必要がある構成設定について説明します。 Skype for Business Server 2019 の展開と構成のプロセスは、Skype for Business Server 2015 とよく似ています。 このセクションでは、パイロットプールの展開の一部として考慮する必要がある重要なポイントについて説明します。 詳細な手順については、展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供する展開ドキュメントで、「Skype for Business Server 2019 への外部ユーザーアクセスの展開」を参照してください。
ms.openlocfilehash: b416ba38646d05f3d10a7d2643c01924fe57020a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238389"
---
# <a name="deploy-pilot-edge-server"></a>パイロット エッジ サーバーの展開

このトピックでは、Skype for Business Server 2019 エッジサーバーを展開する前に知っておく必要がある構成設定について説明します。 Skype for Business Server 2019 の展開と構成のプロセスは、Skype for Business Server 2015 とよく似ています。 このセクションでは、パイロットプールの展開の一部として考慮する必要がある重要なポイントについて説明します。 <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
[**新しいエッジプールの定義**] ウィザードを実行するときに、次の手順に示されているキー構成の設定を確認します。 [**新しいエッジプールの定義**] ウィザードの一部のページのみが表示されることに注意してください。 
  
### <a name="to-define-an-edge-pool"></a>エッジプールを定義するには

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. Skype for Business Server 2019 ノードに移動します。 [**エッジプール**] を右クリックし、[**新しいエッジプール**] をクリックします。
    
     ![[新しいエッジプールの定義] ダイアログボックス](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. エッジプールには、**複数のコンピュータプール**または**単一のコンピュータプール**を使用できます。
    
     ![エッジプールの FQDN ダイアログボックスの定義](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. **[機能の選択**] ページで、フェデレーションまたは xmpp フェデレーションを有効にしないようにします。 フェデレーションと XMPP フェデレーションは、現在、従来のエッジサーバーを介してルーティングされます。 これらの機能は、移行の後のフェーズで構成されます。 

  
5. 次のウィザードページに進んでください。**外部 fqdn**、**内部 ip アドレスの定義**、**外部 ip アドレスの定義**を続行します。
    
6. [ **Next ホップサーバーの定義**] ページで、従来の Edge プールの次ホップのディレクターを選択します。 
    
     ![[次ホップの定義] ダイアログボックス](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. [**フロントエンドまたは仲介プールの関連付け**] ページで、この時点ではプールをこのエッジプールに関連付けないでください。 外部メディアトラフィックは、現在、従来のエッジサーバーを介してルーティングされています。 この設定は、移行の後のフェーズで構成されます。 
    
     ![[フロントエンドプールの関連付け] ダイアログボックス](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. [**完了**] をクリックして、トポロジを**公開**します。 
    
9. 展開ドキュメントの手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
展開ドキュメントのトピックのガイドラインに従うことが非常に重要です。 このセクションでは、これらのサーバーの役割をインストールするときの構成設定について、いくつかのガイダンスを示しました。 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
これで、Skype for Business Server 2019 Edge server の展開と並行してレガシエッジサーバーを展開することができます。 両方の展開が適切に実行されていることを確認し、サービスが開始されていることを確認します。次のフェーズに移行する前に、各展開を管理することができます。 
  

