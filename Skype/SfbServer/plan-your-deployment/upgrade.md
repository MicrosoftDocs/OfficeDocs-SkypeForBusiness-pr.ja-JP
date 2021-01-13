---
title: Skype for Business Server 2015 へのアップグレードを計画する
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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: '概要: Skype for Business Server 2015 へのアップグレードを計画する際に考慮する必要がある点について確認します。 Microsoft Evaluation Center から Skype for Business Server 2015 の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 69b1d9df20330ad0baecbc1c5abe59e76808185a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831977"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Skype for Business Server 2015 へのアップグレードを計画する
 
概要: Skype for Business Server 2015 へのアップグレードを計画する際に考慮する必要がある項目について学習します。 Microsoft Evaluation Center から Skype for Business Server 2015 の無料試用版を次の場所からダウンロードします [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。
  
Skype for Business Server 2015 へのアップグレード計画の一環として、このトピックを使用して、Skype for Business Server 2015 への推奨されるアップグレード パス、In-Place アップグレードのしくみ、サポートされている共存シナリオ、およびアップグレード プロセスがどのようになるかを理解します。

> [!NOTE]
> 一時アップグレードは Skype for Business Server 2015 で利用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 共存がサポートされている場合は [、「Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) への移行」を参照してください。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Skype for Business Server 2015 への推奨されるアップグレード パス

 Lync Server 2013、Lync Server 2010、または Office Communications Server 2007 R2 から Skype for Business Server 2015 にアップグレードするには、次のアップグレード パスを使用します。
  
> [!CAUTION]
> In-Placeアップグレードでは、会議ディレクトリが Lync Server 2013 から Skype for Business Server 2015 に自動的に移動されます。 ただし、会議ディレクトリを手動で移動する場合は、Skype for Business Server 2015 管理シェルを使用することが非常に重要です。 Lync Server 2013 管理シェルを使用して会議ディレクトリを Lync Server 2013 から Skype for Business Server 2015 に移動すると、データ損失が発生する可能性があります。 一般に、Skype for Business Server 2015 を任意の容量で使用する場合は常に、Skype for Business Server 2015 ツール セットを使用する必要があります。  
  
|**バージョン**|**推奨**|
|:-----|:-----|
|Lync Server 2013  <br/> | アップグレードするには、プールに関連付けられている各サーバーで Skype for Business Server トポロジ ビルダーと新しい In-Place アップグレード機能を使用します。 詳細 [な手順については、「Lync Server 2013 から Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) へのアップグレードを計画する」および [「Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) へのアップグレード」を参照してください。 <br/> |
|Lync Server 2010 + Lync Server 2013 (デュアル モード)  <br/> |まず、Lync Server 2013 にアップグレードしてから、新しいアップグレード機能を使用して Skype for Business Server 2015 In-Placeします。 ただし、トポロジがプライマリ Lync Server 2010 の場合は、Lync Server 2013 コンポーネントを Lync Server 2010 にロールバックしてから、Skype for Business Server 2015 に直接アップグレードすることもできます。 この場合、In-Place アップグレードを利用することはできません。また、Lync Server 2010 と Skype for Business Server 2015 の間で直接の共同存在を使用します。 3 つの存在はサポートされていませんが、共同存在はサポートされています。  <br/> |
|Lync Server 2010  <br/> |新しい Skype for Business Server 2015 プールを表示し、ユーザーをこの新しいプールに移行します。 その後、古い Lync Server 2010 プールを使用停止にできます。 Lync Server 2010 から Skype for Business Server 2015 へのアップグレードは、Lync Server 2010 から Lync Server 2013 へのアップグレードに似ています。 [「Lync Server 2010 から Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)への移行」を参照してください。  <br/> |
|Office Communications Server 2007 R2  <br/> | 次の 2 つのオプションのいずれかを選択します。 <br/>  新しい Skype for Business Server 2015 環境をセットアップします。 <br/>  または、ハードウェアとソフトウェアが Skype for Business Server 2015 の要件を満たしている場合は、Lync Server 2013 にアップグレードしてから、新しい In-Place アップグレード機能を使用して Skype for Business Server 2015 にアップグレードします。 詳細については [、「Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) のサーバー要件」および [「Office Communications Server 2007 R2 から Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616)への移行」を参照してください。  <br/> |
   
> [!NOTE]
> SQL Server 2014 は Skype for Business Server 2015 でサポートされますが、Lync Server 2013 ではサポートされていません。 SQL Server 2012 から SQL Server 2014 にアップグレードする場合は、このドキュメントで説明するように、まず In-Place Upgrade 方法を使用してプールを Skype for Business Server 2015 にアップグレードする必要があります。 その後、SQL Server 2012 から SQL Server 2014 にアップグレードできます [。「2014](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx)年にアップグレードする」をSQL Serverしてください。 データベース要件の詳細については [、「Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)のサーバー要件」を参照してください。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Lync Server 2013 から Skype for Business Server 2015 へのアップグレードを計画する
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

新しいアップグレード機能を使用して、Lync Server 2013 システムを Skype for Business Server 2015 In-Placeアップグレードできます。 一時アップグレードは、証明書のバックアップ、サーバー コンポーネントのアンインストール、ローカル データベースのアップグレード、および Skype for Business Server 2015 の役割のインストールを行う 1 回クリックのソリューションを提供します。 一時アップグレードでは、既存のハードウェアとサーバーへの投資を維持し、Skype for Business Server 2015 を展開するための全体的なコストを削減します。
  
> [!NOTE]
> In-Placeアップグレードでは、Skype for Business Server にアップグレードするときに同じハードウェアを使用できます。 ただし、同じハードウェアを再利用しても、同じパフォーマンス容量に変換されるわけではありません。 Lync Server 2013 と Skype for Business Server 2015 のパフォーマンス負荷が同じになるはずはありません。 
  
> [!NOTE]
> In-Placeは、Skype for Business Server の高可用性や障害復旧をサポートしません。 
  
一時アップグレードでは、Lync Server 2013 プールをオフラインにし、Skype for Business Server 2015 プールにアップグレードします。 
  
### <a name="create-an-in-place-upgrade-plan"></a>アップグレード計画In-Place作成する

以下を含むプランを作成します。
  
1. 現在のトポロジの理解。
    
    > [!NOTE]
    > アップグレードを実行する前に、Lync Server 2013 の LRS 管理ツールIn-Placeしてください。 Lync Server 2013 の LRS 管理ツールは、Skype for Business Server 2015 と共存できません。 アップグレードを実行In-Place、新しい LRS 管理ツールをインストールします。 詳細 [については、「Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015」](https://go.microsoft.com/fwlink/?LinkID=544807) を参照してください。
  
2. アップグレードのプライマリ プール。
    
3. アーカイブ データベースと監視データベースをアップグレードするか、新しいデータベースを作成するか。
    
4. 使用In-Placeアップグレード方法: オフラインまたはユーザーの移動。 ユーザーの移動の一環として、プライマリ プールに関連付けられているグローバル会議ディレクトリも移行する必要があります。 
    
5. 影響を受け取るユーザーの通信計画。
    
6. アップグレードが失敗した場合のバックアップ計画。
    
アップグレード中にプライマリ プールに入っているユーザーは、アップグレードが完了するまでサービスを使用することはできません。 作業中のセカンダリ プールがある場合は、アップグレード前にユーザーをセカンダリ プールに移動することで、ユーザーへの影響を回避できます。 アップグレード後、ユーザーをプライマリ プールに戻します。
  
### <a name="in-place-upgrade-methods"></a>一時アップグレードの方法

アップグレードには、次の 2 つのIn-Placeがあります。 
  
- ユーザーの移動方法。ユーザーのダウンタイムを必要としません。 
    
- Offline メソッド。ダウンタイムが必要です。
    
オフライン 方式のアップグレードは、メンテナンス期間中にスケジュールし、ダウンタイムをユーザーに通知することをお勧めします。
  
> [!NOTE]
> Lync Server 2013 でペアのプールをアップグレードし、両方のプールを Skype for Business Server 2015 にアップグレードする場合。 最初のプールをアップグレードした直後に、2 番目のプールをアップグレードしてください。 1 つのプールが Lync Server 2013 を実行し、2 番目のプールが Skype for Business Server 2015 を実行している場合、障害復旧オプションは最小化されます。 たとえば、1 つのプールが 2013 を実行し、2 つ目が 2015 で障害が発生した場合、ペアのプールが同じバージョンではない場合、障害モードではプールフェールオーバーがサポートされないので、データ損失が発生する可能性があります。 
  
#### <a name="in-place-upgrade-offline-method"></a>一時アップグレードのオフライン方式

ユーザーをユーザー プール間で移動しない場合は、この方法を使用します。 アップグレード中、ユーザーは Lync または Skype for Business サービスを使用することはできません。 
  
次の図は、このプロセスの概要を示しています。
  
![Lync 2013 から Skype ユーザーへのオフライン](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> ペアのプールがある場合は、アップグレードの前にペアを解除しないでください。 
  
サーバー プールのアップグレードを開始したら、プール全体のアップグレードを完了する必要があります。 Skype for Business Server では、プールの一部のみをアップグレードできません。 
  
#### <a name="move-users-method-no-user-downtime"></a>ユーザーの移動方法 (ユーザーのダウンタイムなし)
<a name="bkmk_MoveUsersMethod"> </a>

この方法を使用するには、アップグレードを開始する前にユーザーを別のプールに移動します。 アップグレード中、ユーザーは Lync サービスを使用できます。 アップグレードされたプールに移動した後は、Skype for Business を使用できます。 次の図は、このプロセスの概要を示しています。
  
> [!IMPORTANT]
> ユーザーの移動の一環として、プライマリ プールに関連付けられているグローバル会議ディレクトリも移行する必要があります。 PSTN ダイヤルイン会議では、ConferenceID は、ペアのプールではなく、アップグレードされるプールに解決されます。 したがって、アップグレード中にプールでスケジュールされた PSTN 会議に引き続きアクセスする場合は、会議ディレクトリを移動する必要があります。 
  
![プールがアップグレードされる前に別のプールに移動され、アップグレード後にプールに戻るユーザーを示すプール図。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>ハードウェア アップグレード用にユーザーを移動する
<a name="bkmk_MoveUsersMethod"> </a>

 ハードウェアが [Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)のサーバー要件を満たしない場合は、新しい Skype for Business Server 2015 環境をセットアップし、ユーザーをそこに移動します。 次の図は、Lync Server 2010 からのアップグレードに関するこのプロセスの概要を示しています。 
  
![Skype for Business Server 2015 および使用停止中の Lync Server プールに移動される Lync Server プライマリ フロント エンド プールのユーザーを示すスレーン 図。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>一括アップグレード プロセス

 次の手順を使用して、Lync Server 2013 から Skype for Business Server 2015 にアップグレードします。
  
1. アップグレードの前に、すべてのデータベースをバックアップします。
    
2. アップグレードするサービスはすべて実行中の状態にしてください。
    
3. トポロジ ビルダーを使用してトポロジ ファイルをアップグレードおよび公開します。
    
4. すべてのフロントエンド サーバー上のすべてのサービスを停止します。
    
5. Skype for Business Server に必要な新しい前提条件をインストールします。
    
6. 各フロントエンド サーバーで、アップグレードの開始In-Placeします。
    
7. アップグレードが完了したら、すべてのサービスを再起動します。
    
   - フロントエンド プールの場合は、Start-CsPool コマンドを使用してサービスを再起動します。
    
   - フロントエンド サーバー以外のサーバーの場合は、Start-CSWindowsService を使用します。
    
> [!NOTE]
>  既存のアーカイブ データベースと監視データベースをアップグレードしない場合は、トポロジをアップグレードする前に依存関係を削除してください。 新しいアーカイブ データベースと監視データベースを作成する場合は、アップグレード中に新しい SQL ストアを作成し、それをプールに関連付けできます。 これを行う手順については、[トピック「Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)へのアップグレード」を参照してください。 >アップグレードでは、Skype for Business Server の高可用性や障害復旧はサポートされません。 ユーザーのサービスが中断しないようにするには、ユーザーの移動方法 (ユーザーのダウンタイムなし [)](upgrade.md#bkmk_MoveUsersMethod) を使用してアップグレードします。> アップグレード プロセス中に、xds-replica はディスク ドライブ上の最も空き領域の多いローカル共有フォルダーに配置されます。 そのディスクが後で削除されると、サービスが開始されないなどの問題が発生する可能性があります。
  
### <a name="upgrade-order"></a>アップグレード順序

トポロジを内部から外部にアップグレードします。 最初に、すべてのプール、エッジ サーバー、最後に中央管理ストア (CMS) プールをアップグレードします。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 認証に関する考慮事項

Web サービスに Kerberos 認証を使用する場合は、アップグレードの完了後に Kerberos アカウントを再割り当てし、パスワードIn-Placeリセットする必要があります。 これを行う方法については [、「Kerberos 認証の設定」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=530342)。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Lync Server 2013 および Lync Server 2010 との共存のサポート
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 は Lync Server 2013 または Lync Server 2010 と同じトポロジで実行できますが、3 つすべてが同じトポロジに含めである必要があります。
  
Lync Server 2010 と Lync Server 2013 の間に存在する場合は、トポロジ全体を Lync Server 2013 にアップグレードしてから、In-Place アップグレードを使用して Skype for Business Server 2015 にアップグレードする方法をお勧めします。 詳細については [、「Lync Server 2010 から Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)への移行」を参照してください。
  
トポロジが主に Lync Server 2010 である場合は、トポロジを Skype for Business Server 2015 にアップグレードする前に、Lync Server 2013 コンポーネントを Lync Server 2010 にロールバックします。 この場合、In-Place アップグレードの利点は失われるので、Lync Server 2010 と Skype for Business Server 2015 の間にトポロジが存在します。
  
次の図は、Skype for Business Server 2015 と Lync Server 2013 および Lync Server 2010 の共存のサポートを示しています。
  
![Skype for Business Server 2015 と Lync Server 2013 または Lync Server 2010 の共存サポートを示す図。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>既存の存続可能ブランチ アプライアンスおよびサーバーを使用したアップグレード プロセス
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 は、存続可能ブランチ アプライアンス (SBA) または存続可能ブランチ サーバー (SBS) の In-Place アップグレードをサポートしません。
  
ただし、Skype for Business Server データセンターと Lync Server 2010 または Lync Server 2013 SBA/SBS の共存はサポートされています。 
  
ブランチが関連付けられた Lync Server 2013 フロントエンド (FE) プールの In-Place アップグレードを計画する場合は、既存のユーザーを Lync Server 2013 SBA/SBS のままにすることができます。 アップグレード中、SBA/SBS ユーザーは復元モードに切り替わるので、アップグレードが完了すると通常の機能に戻ります。 復元モード中のユーザー エクスペリエンスの詳細については [、Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx)のブランチ サイトの復元機能を参照してください。
  
Lync Server 2010 トポロジを Skype for Business Server 2015 に移行する場合、Lync Server 2013 への移行と同様に、SBA/SBS をトポロジに再追加する必要があります。 必要な手順については、「Lync [Server 2013](https://technet.microsoft.com/library/jj688026.aspx)フロントエンド プールへの存続可能ブランチ アプライアンスの接続」を参照してください。
  
Lync Server 2010 と Lync Server 2013 の共存トポロジについては、「Lync Server 2013 および Lync Server 2010 との共存のサポート」セクションで行った推奨事項に最初に合わせてください。
  
## <a name="see-also"></a>関連項目
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Skype for Business Server 2015 へのアップグレード](../deploy/upgrade-to-skype-for-business-server.md)
  
[Skype for Business Server 2015 の環境要件](requirements-for-your-environment/environmental-requirements.md)
  
[Skype for Business Server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)
