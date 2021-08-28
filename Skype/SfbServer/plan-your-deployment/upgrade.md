---
title: 2015 年にアップグレードSkype for Business Serverする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: '概要: 2015 年にアップグレードを計画する際に考慮すべき点Skype for Business Serverします。 Microsoft 評価センターから Skype for Business Server 2015 の無料試用版をダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: a3a36bb7c1acbf5334c108429076aa8126860041
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630411"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>2015 年にアップグレードSkype for Business Serverする
 
概要: 2015 年にアップグレードを計画する際に考慮すべき点Skype for Business Serverします。 Microsoft 評価センターから Skype for Business Server 2015 の無料試用版をダウンロードします [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。
  
Skype for Business Server 2015 へのアップグレード計画の一環として、このトピックを使用して、Skype for Business Server 2015 への推奨アップグレード パス、In-Place アップグレードのしくみ、サポートされている共存シナリオ、およびアップグレード プロセスの外観を理解します。

> [!NOTE]
> インプレイス アップグレードは 2015 年Skype for Business Serverでしたが、2019 年Skype for Business Serverではサポートされていません。 サイド バイ サイドの共存がサポートされています。詳細については[、「Migration to Skype for Business Server 2019」](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)を参照してください。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>2015 年に推奨されるアップグレード Skype for Business Serverパス

 Lync Server 2013、Lync Server 2010、または Office Communications Server 2007 R2 から Skype for Business Server 2015 にアップグレードするには、次のアップグレード パスを使用します。
  
> [!CAUTION]
> In-Placeアップグレードでは、会議ディレクトリが Lync Server 2013 から 2015 Skype for Business Serverされます。 ただし、会議ディレクトリを手動で移動する場合は、2015 管理シェルのSkype for Business Server重要です。 Lync Server 2013 管理シェルを使用して会議ディレクトリを Lync Server 2013 から Skype for Business Server 2015 に移動すると、データ損失が発生する可能性があります。 一般に、任意の容量で Skype for Business Server 2015 を操作する場合は常に、Skype for Business Server ツール セットを使用する必要があります。  
  
|**バージョン**|**推奨事項**|
|:-----|:-----|
|Lync Server 2013  <br/> | アップグレードするには、プールに関連Skype for Business Server各サーバーで In-Place トポロジ ビルダーと新しいアップグレード機能を使用します。 詳細[な手順については、「Lync Server 2013 から Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013)へのアップグレードを計画する」および[「Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)へのアップグレード」を参照してください。 <br/> |
|Lync Server 2010 + Lync Server 2013 (デュアル モード)  <br/> |まず、Lync Server 2013 にアップグレードし、新しいアップグレード機能を使用して Skype for Business Server 2015 In-Placeします。 ただし、トポロジがプライマリ Lync Server 2010 の場合は、Lync Server 2013 コンポーネントを Lync Server 2010 にロールバックしてから、直接 Skype for Business Server 2015 にアップグレードすることもできます。 この場合、In-Place アップグレードを利用することはできません。Lync Server 2010 と Skype for Business Server 2015 の間で直接共同存在を使用します。 Tri-existence はサポートされていませんが、共同存在はサポートされています。  <br/> |
|Lync Server 2010  <br/> |2015 年 2015 Skype for Business Server新しいプールを立ち上げ、ユーザーをこの新しいプールに移行します。 その後、古い Lync Server 2010 プールを使用停止できます。 Lync Server 2010 から Skype for Business Server 2015 へのアップグレードは、Lync Server 2010 から Lync Server 2013 へのアップグレードに似ています。 「Lync [Server 2010 から Lync Server 2013 への移行」を参照](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013)してください。  <br/> |
|Office Communications Server 2007 R2  <br/> | 次の 2 つのオプションのいずれかを選択します。 <br/>  2015 年Skype for Business Server環境をセットアップします。 <br/>  または、ハードウェアとソフトウェアが Skype for Business Server 2015 の要件を満たしている場合は、Lync Server 2013 にアップグレードし、新しい In-Place アップグレード機能を使用して Skype for Business Server 2015 にアップグレードします。 詳細については[、「Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)のサーバー要件」および[「Office Communications Server 2007 R2 から Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-office-communications-server-2007-r2-to-lync-server-2013)への移行」を参照してください。  <br/> |
   
> [!NOTE]
> SQL Server 2014 は 2015 年Skype for Business Serverサポートされますが、Lync Server 2013 ではサポートされていません。 SQL Server 2012 から SQL Server 2014 にアップグレードする場合は、このドキュメントで説明するように、In-Place Upgrade メソッドを使用してプールを最初に Skype for Business Server 2015 にアップグレードする必要があります。 その後、2012 SQL Server から 2014 SQL Serverにアップグレードできます。「Upgrade [to SQL Server 2014」を参照](/sql/database-engine/install-windows/upgrade-sql-server?viewFallbackFrom=sql-server-2014)してください。 データベース要件の詳細については[、「Server requirements for Skype for Business Server 2015」を参照](requirements-for-your-environment/server-requirements.md)してください。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Lync Server 2013 から 2015 年Skype for Business Serverする計画
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Lync Server 2013 システムを 2015 Skype for Business Serverアップグレード機能を使用In-Placeアップグレードできます。 インプレイス アップグレードは、証明書をバックアップし、サーバー コンポーネントをアンインストールし、ローカル データベースをアップグレードし、Skype for Business Server 2015 の役割をインストールする 1 回Skype for Business Serverソリューションを提供します。 インプレイス アップグレードでは、既存のハードウェアとサーバーへの投資を維持し、2015 年に展開するための全体的なコストを削減Skype for Business Serverしています。
  
> [!NOTE]
> In-Placeアップグレードでは、アップグレード時に同じハードウェアを使用Skype for Business Server。 ただし、同じハードウェアを再利用しても、同じパフォーマンス容量には変換されない。 Lync Server 2013 および 2015 および 2015 Skype for Business Serverのパフォーマンス負荷が同一である必要はありません。 
  
> [!NOTE]
> In-Placeアップグレードは、高可用性または障害復旧をサポートSkype for Business Server。 
  
一時アップグレードには、Lync Server 2013 プールをオフラインにし、それを 2015 年Skype for Business Serverする必要があります。 
  
### <a name="create-an-in-place-upgrade-plan"></a>アップグレードプランIn-Place作成する

次の内容を含むプランを作成します。
  
1. 現在のトポロジの理解。
    
    > [!NOTE]
    > Lync Server 2013 の LRS 管理ツールをアンインストールしてから、アップグレードIn-Placeしてください。 Lync Server 2013 の LRS 管理ツールは、2015 年Skype for Business Serverできません。 アップグレードを実行In-Place新しい LRS 管理ツールをインストールします。 詳細については、「Microsoft Lync Room System Administrative [Web Portal for Skype for Business Server 2015」](https://go.microsoft.com/fwlink/?LinkID=544807)を参照してください。
  
2. アップグレードのプライマリ プール。
    
3. アーカイブ データベースと監視データベースをアップグレードするか、新しいデータベースを作成するか。
    
4. 使用In-Placeアップグレード方法: オフラインまたはユーザーの移動。 ユーザーの移動の一環として、プライマリ プールに関連付けられているグローバル会議ディレクトリも移行する必要があります。 
    
5. 影響を受け取ったユーザーの通信計画。
    
6. アップグレードが失敗した場合のバックアップ計画。
    
アップグレード中にプライマリ プール内にあるユーザーは、アップグレードが完了するまでサービスを使用することはできません。 セカンダリ プールが動作している場合は、アップグレード前にセカンダリ プールにユーザーを移動することで、ユーザーに影響を与えるのを避けできます。 アップグレード後、ユーザーをプライマリ プールに戻します。
  
### <a name="in-place-upgrade-methods"></a>インプレイス アップグレードの方法

アップグレードには、次の 2 つのIn-Placeがあります。 
  
- ユーザーのダウンタイムを必要としません。 
    
- ダウンタイムが必要な Offline メソッド。
    
メンテナンス 期間中にオフライン メソッドのアップグレードをスケジュールし、ユーザーにダウンタイムを通知することをお勧めします。
  
> [!NOTE]
> Lync Server 2013 でペアプールをアップグレードし、両方のプールを 2015 年Skype for Business Serverする場合。 最初のプールをアップグレードした直後に、2 番目のプールをアップグレードしてください。 1 つのプールが Lync Server 2013 を実行し、2 番目のプールが 2015 年Skype for Business Server実行されている場合、障害復旧オプションは最小限に抑わります。 たとえば、1 つのプールが 2013 を実行し、2 つ目が 2015 で障害が発生した場合、ペアのプールが同じバージョンではない場合に障害モードでプールのフェールオーバーがサポートされないので、データ損失が発生する可能性があります。 
  
#### <a name="in-place-upgrade-offline-method"></a>インプレイス アップグレード Offline メソッド

ユーザー プール間でユーザーを移動しない場合は、このメソッドを使用します。 アップグレード中、ユーザーは Lync またはサービスを使用Skype for Businessされます。 
  
次の図は、このプロセスの概要を示しています。
  
![Lync 2013 ユーザー Skypeオフラインにする](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> ペアのプールがある場合は、アップグレード前にプールのペアリングを解除しないでください。 
  
サーバー プールのアップグレードを開始したら、プール全体のアップグレードを完了する必要があります。 Skype for Business Serverプールの一部のみをアップグレードする機能はサポートされていません。 
  
#### <a name="move-users-method-no-user-downtime"></a>Move Users メソッド (ユーザーのダウンタイムなし)
<a name="bkmk_MoveUsersMethod"> </a>

この方法を使用するには、アップグレードを開始する前に、ユーザーを別のプールに移動します。 アップグレード中、ユーザーは Lync サービスを使用できます。 アップグレードされたプールに移動した後、アップグレードしたプールを使用Skype for Business。 次の図は、このプロセスの概要を示しています。
  
> [!IMPORTANT]
> ユーザーの移動の一環として、プライマリ プールに関連付けられているグローバル会議ディレクトリも移行する必要があります。 PSTN ダイヤルイン会議は、ペアリングされたプールではなく、アップグレードされるプールに対して ConferenceID を解決します。 そのため、アップグレード中にプールで PSTN 会議をスケジュールする場合は、会議ディレクトリを移動する必要があります。 
  
![プールがアップグレードされる前に別のプールに移動され、アップグレード後にプールに戻されるユーザーを示すスイム図。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>ハードウェア アップグレード用にユーザーを移動する
<a name="bkmk_MoveUsersMethod"> </a>

 ハードウェアが[Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)のサーバー要件を満たSkype for Business Server 2015 環境をセットアップし、ユーザーをそこに移動します。 次の図は、Lync Server 2010 からのアップグレードのためのこのプロセスの概要を示しています。 
  
![Lync Server プライマリ フロント エンド プール内のユーザーが 2015 年 2015 年に移動され、Lync Server プールが使用停止Skype for Business Serverを示すスイム レーン図。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>一括アップグレード プロセス

 次の手順を使用して、Lync Server 2013 から Skype for Business Server 2015 にアップグレードします。
  
1. アップグレードの前に、すべてのデータベースをバックアップします。
    
2. アップグレードするサービスすべてが実行中の状態にあるか確認します。
    
3. トポロジ ビルダーを使用してトポロジ ファイルをアップグレードして発行します。
    
4. すべてのフロントエンド サーバー上のすべてのサービスを停止します。
    
5. インストールに必要な新しい前提条件をSkype for Business Server。
    
6. 各フロントエンド サーバーで、アップグレードの開始In-Placeします。
    
7. アップグレードが完了したら、すべてのサービスを再起動します。
    
   - フロントエンド プールの場合は、Start-CsPool コマンドを使用してサービスを再起動します。
    
   - フロントエンド 以外のサーバーの場合は、Start-CSWindowsService を使用します。
    
> [!NOTE]
>  既存のアーカイブ データベースと監視データベースをアップグレードしない場合は、トポロジをアップグレードする前に依存関係を削除します。 アップグレード中に新しいアーカイブ データベースと監視データベースを作成する場合は、新しいアーカイブ SQL作成し、プールに関連付けできます。 これを行う方法については、「Upgrade[to Skype for Business Server 2015」を参照してください](../deploy/upgrade-to-skype-for-business-server.md)。 >インプレイス アップグレードでは、高可用性または障害復旧がサポートSkype for Business Server。 ユーザーのサービスを中断しないようにするには、Move [Users](upgrade.md#bkmk_MoveUsersMethod) メソッド (ユーザーのダウンタイムなし) を使用して upgrade.> アップグレード プロセス中に、ディスク ドライブ上の最も空き領域の多いローカル共有フォルダーに xds-replica を配置します。 そのディスクが後で削除された場合は、サービスが開始されないなどの問題が発生する可能性があります。
  
### <a name="upgrade-order"></a>アップグレードの順序

トポロジを内部から外部にアップグレードします。 最初にすべてのプールをアップグレードし、次にエッジ サーバー、最後に中央管理ストア (CMS) プールをアップグレードします。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 認証に関する考慮事項

Web サービスに Kerberos 認証を使用する場合は、Kerberos アカウントを再割り当てし、アップグレードの完了後にパスワードIn-Placeリセットする必要があります。 これを行う方法については [、「Kerberos 認証のセットアップ」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-kerberos-authentication)。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Lync Server 2013 および Lync Server 2010 との共存のサポート
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Lync Server 2013 または Lync Server 2010 と同じトポロジで Skype for Business Server 2015 を実行できますが、3 つすべてが同じトポロジに含めである必要があります。
  
Lync Server 2010 と Lync Server 2013 の間に共同で存在する場合は、トポロジ全体を Lync Server 2013 にアップグレードしてから、In-Place アップグレードを使用して Skype for Business Server 2015 にアップグレードをお勧めします。 詳細については [、「Lync Server 2010 から Lync Server 2013 への移行」を参照してください](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013)。
  
トポロジが主に Lync Server 2010 の場合は、Lync Server 2013 コンポーネントを Lync Server 2010 にロールバックしてから、トポロジを Skype for Business Server 2015 にアップグレードします。 この場合、In-Place アップグレードの利点を失い、Lync Server 2010 と 2015 の間にSkype for Business Serverがあります。
  
次の図は、Lync Server 2013 および Lync Server 2010 Skype for Business Server 2015 との共存サポートを示しています。
  
![Lync Server 2013 または Lync Server 2010 Skype for Business Server 2015 の共存サポートを示す図。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>既存の存続可能ブランチ アプライアンスとサーバーを使用したアップグレード プロセス
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 では、存続可能ブランチ アプライアンス (SBA) または存続可能ブランチ サーバー (SBS) の In-Place アップグレードはサポートされていません。
  
ただし、Lync Server 2010 または Lync Server 2013 SBA/SBS Skype for Business Serverデータセンターの共存はサポートされています。 
  
関連付けられたブランチを持つ Lync Server 2013 フロントエンド (FE) プールの In-Place アップグレードを計画する場合は、既存のユーザーを Lync Server 2013 SBA/SBS のままにすることができます。 アップグレード中、SBA/SBS ユーザーは復元モードに入り、アップグレードが完了すると通常の機能に戻ります。 復元モード中のユーザーエクスペリエンスの詳細については [、「Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-features)のブランチ サイトの復元機能」を参照してください。
  
Lync Server 2010 トポロジを Skype for Business Server 2015 に移行する場合、SBA/SBS は Lync Server 2013 への移行と同様に、トポロジに再追加する必要があります。 必要な手順については、「存続可能ブランチ アプライアンスを [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool)フロントエンド プールに接続する」を参照してください。
  
Lync Server 2010 と Lync Server 2013 の共存トポロジについては、まず「Lync Server 2013 および Lync Server 2010 との共存のサポート」セクションで行われた推奨事項に合わせてください。
  
## <a name="see-also"></a>関連項目
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[2015 Skype for Business Serverへのアップグレード](../deploy/upgrade-to-skype-for-business-server.md)
  
[2015 年の環境Skype for Business Server要件](requirements-for-your-environment/environmental-requirements.md)
  
[2015 年のサーバー Skype for Business Server要件](requirements-for-your-environment/server-requirements.md)