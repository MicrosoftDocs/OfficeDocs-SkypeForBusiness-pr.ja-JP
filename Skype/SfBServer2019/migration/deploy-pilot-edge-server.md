---
title: パイロットのエッジ サーバーを展開します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: このトピックでは、Skype をビジネス 2019 エッジ サーバーを展開する前に注意する必要があります構成の設定が強調表示されます。 ビジネス サーバー 2019 の Skype の展開と構成のプロセスは、ビジネス サーバー 2015 の Skype に非常に似ています。 のみ、このセクションには、パイロット プール展開の一環として検討する必要がある重要なポイントが強調表示されます。 詳細な手順を参照してください Skype で外部ユーザー アクセスを導入するビジネス サーバー 2019 の展開に関するドキュメントは、展開プロセスについて説明し、外部ユーザー アクセスの構成情報も示されます。
ms.openlocfilehash: 3ae1508c56ac3240cfb9904415090ff1bdf18677
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029861"
---
# <a name="deploy-pilot-edge-server"></a>パイロットのエッジ サーバーを展開します。

このトピックでは、構成の設定をする必要があります、Skype をビジネス 2019 エッジ サーバーを展開する前に強調表示されます。 ビジネス サーバー 2019 の Skype の展開と構成のプロセスは、ビジネス サーバー 2015 の Skype に非常に似ています。 のみ、このセクションには、パイロット プール展開の一環として検討する必要がある重要なポイントが強調表示されます。 <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
**新しいエッジ プールの定義**ウィザードを使って移動すると、次の手順に示すようにキーの構成設定を確認します。 **新しいエッジ プールの定義**ウィザードのいくつかのページのみが表示されることに注意してください。 
  
### <a name="to-define-an-edge-pool"></a>エッジのプールを定義するのには

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. ビジネス サーバー 2019 ノードの Skype に移動します。 **エッジ プール**を右クリックし、[**新しいエッジ プール**] をクリックします。
    
     ![[新しいエッジ プール] ダイアログ ボックスを定義します。](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. エッジ プールは、**複数のコンピューター プール**または**1 台のコンピューターのプール**を使用できます。
    
     ![エッジ プール FQDN] ダイアログ ボックスを定義します。](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. [**機能の選択**] ページで、有効にしないでフェデレーションまたは XMPP フェデレーション。 フェデレーションと XMPP フェデレーションは両方とも現在サーバー経由でルーティング レガシー エッジ。 これらの機能は、移行の以降のフェーズで構成されます。 

  
5. 完了ウィザード ページを続行:**外部 Fqdn**、**内部の IP アドレスの定義**、および**外部 IP アドレスを定義**します。
    
6. **次ホップのサーバーの定義**] ページで、従来のエッジ プールの次ホップのためにディレクターを選択します。 
    
     ![次ホップ] ダイアログ ボックスを定義します。](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. **フロント エンドを関連付けるまたは仲介プール**] ページで、関連づけられていないプールこのエッジ プールをこの時点で。 外部メディア現在トラフィックが従来のエッジ サーバーを経由します。 この設定は、移行の以降のフェーズで構成されます。 
    
     ![関連付けるフロント エンド プール] ダイアログ ボックス](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. **完了**し、トポロジの**発行**] をクリックします。 
    
9. 新しいエッジ サーバー上のファイルをインストール、構成、証明書およびサービスを開始する導入マニュアルの手順に従います。 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
展開に関するドキュメントのトピックのガイドラインに従うことが非常に重要です。 このセクションが表示されるだけのガイダンス構成の設定にこれらのサーバー ロールをインストールするとき。 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
これで、Skype のビジネス サーバー 2019 エッジ サーバーの展開と並行して、展開、レガシ エッジ サーバーが必要です。 確認両方の展開が正常に動作して、サービスが開始されると、次の段階に進む前にそれぞれの展開を管理することができます。 
  

