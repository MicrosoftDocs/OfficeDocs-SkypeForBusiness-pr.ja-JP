---
title: Skype for Business Server 2015 にアップグレードする予定
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: '概要: Skype for Business Server 2015 へのアップグレードを計画するときに考慮すべき点について説明します。'
ms.openlocfilehash: 0b31234bbb0cbc5c2475b241b810430f7595f411
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860598"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Skype for Business Server 2015 にアップグレードする予定
 
概要: Skype for Business Server 2015 へのアップグレードを計画するときに考慮すべき点について説明します。
  
Skype for Business Server 2015 にアップグレードする計画の一環として、このトピックを使用して、Skype for Business Server 2015 への推奨アップグレード パス、In-Place アップグレードのしくみ、サポートされている共存シナリオ、アップグレード プロセスについて理解します。

> [!NOTE]
> インプレース アップグレードは 2015 Skype for Business Serverで利用できましたが、2019 Skype for Business Serverではサポートされなくなりました。 並行共存がサポートされています。詳細については、「[Skype for Business Server 2019 への移行](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)」を参照してください。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Skype for Business Server 2015 への推奨アップグレード パス

 Lync Server 2013、Lync Server 2010、またはOffice Communications Server 2007 R2 から Skype for Business Server 2015 にアップグレードするには、次のアップグレード パスを使用します。
  
> [!CAUTION]
> In-Place アップグレードでは、会議ディレクトリが Lync Server 2013 から Skype for Business Server 2015 に自動的に移動されます。 ただし、会議ディレクトリを手動で移動する場合は、Skype for Business Server 2015 Management Shell を使用することが非常に重要です。 Lync Server 2013 Management Shell を使用して会議ディレクトリを Lync Server 2013 から Skype for Business Server 2015 に移動しようとすると、データ損失が発生する可能性があります。 一般に、Skype for Business Server 2015 を任意の容量で使用するときは常に、Skype for Business Server 2015 ツール セットを使用する必要があります。  
  
|**バージョン**|**推奨事項**|
|:-----|:-----|
|Lync Server 2013  <br/> | アップグレードするには、Skype for Business Server トポロジ ビルダーと、プールに関連付けられている各サーバーの新しいIn-Place アップグレード機能を使用します。 詳細な手順については、「[Lync Server 2013 から Skype for Business Server 2015 にアップグレードする計画](upgrade.md#BKMK_PlanUpgradeFromLync2013)」と[「Skype for Business Server 2015 にアップグレード](../deploy/upgrade-to-skype-for-business-server.md)する」を参照してください。 <br/> |
|Lync Server 2010 + Lync Server 2013 (デュアル モード)  <br/> |まず、Lync Server 2013 にアップグレードし、新しいIn-Placeアップグレード機能を使用して Skype for Business Server 2015 にアップグレードします。 ただし、トポロジがプライマリ Lync Server 2010 の場合は、Lync Server 2013 コンポーネントを Lync Server 2010 にロールバックしてから、Skype for Business Server 2015 に直接アップグレードすることもできます。 この場合、In-Place アップグレードを利用できず、Lync Server 2010 と Skype for Business Server 2015 の間で直接共存します。 Tri-existence はサポートされていませんが、共存はサポートされています。  <br/> |
|Lync Server 2010  <br/> |新しいSkype for Business Server 2015 プールを起動し、ユーザーをこの新しいプールに移行します。 その後、古い Lync Server 2010 プールを使用停止できます。 Lync Server 2010 から Skype for Business Server 2015 へのアップグレードは、Lync Server 2010 から Lync Server 2013 へのアップグレードと似ています。 [Lync Server 2010 から Lync Server 2013 への移行に関するページを](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013)参照してください。  <br/> |
|Office Communications Server 2007 R2  <br/> | 次の 2 つのオプションのいずれかを選択します。 <br/>  新しい Skype for Business Server 2015 環境を設定します。 <br/>  または、ハードウェアとソフトウェアが Skype for Business Server 2015 の要件を満たしている場合は、Lync Server 2013 にアップグレードし、新しいIn-Placeアップグレード機能を使用して 2015 Skype for Business Serverにアップグレードします。 詳細については、「[Skype for Business Server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)と[、Office Communications Server 2007 R2 から Lync Server 2013 への移行」を](/previous-versions/office/lync-server-2013/migration-from-office-communications-server-2007-r2-to-lync-server-2013)参照してください。  <br/> |
   
> [!NOTE]
> SQL Server 2014 は 2015 Skype for Business Serverでサポートされていますが、Lync Server 2013 ではサポートされていません。 SQL Server 2012 から 2014 SQL Serverにアップグレードする場合は、このドキュメントで説明されているように、最初に In-Place Upgrade メソッドを使用して、プールを Skype for Business Server 2015 にアップグレードする必要があります。 その後、SQL Server 2012 から 2014 SQL Serverにアップグレードできます。「[SQL Server 2014 へのアップグレード](/sql/database-engine/install-windows/upgrade-sql-server?viewFallbackFrom=sql-server-2014)」を参照してください。 データベース要件の詳細については、「[Skype for Business Server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)」を参照してください。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Lync Server 2013 から Skype for Business Server 2015 へのアップグレードを計画する
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

新しい In-Place アップグレード機能を使用して、Lync Server 2013 システムを 2015 Skype for Business Serverにアップグレードできます。 インプレース アップグレードは、証明書をバックアップし、サーバー コンポーネントをアンインストールし、ローカル データベースをアップグレードし、Skype for Business Server 2015 ロールをインストールするワンクリック ソリューションを提供します。 インプレース アップグレードでは、既存のハードウェアとサーバーへの投資を維持し、2015 Skype for Business Server展開するための全体的なコストを削減します。
  
> [!NOTE]
> In-Place アップグレードでは、Skype for Business Serverにアップグレードするときに同じハードウェアを使用できます。 ただし、同じハードウェアを再利用しても、同じパフォーマンス容量には変換されません。 Lync Server 2013 と Skype for Business Server 2015 のパフォーマンス負荷が同じになることは想定しないでください。 
  
> [!NOTE]
> In-Placeアップグレードでは、Skype for Business Serverの高可用性またはディザスター リカバリーはサポートされません。 
  
インプレース アップグレードには、Lync Server 2013 プールをオフラインにして、Skype for Business Server 2015 プールにアップグレードする必要があります。 
  
### <a name="create-an-in-place-upgrade-plan"></a>In-Placeアップグレード プランを作成する

次を含むプランを作成します。
  
1. 現在のトポロジの理解。
    
    > [!NOTE]
    > In-Placeアップグレードを実行する前に、Lync Server 2013 の LRS 管理 ツールをアンインストールしてください。 LRS 管理 ツール for Lync Server 2013 は、Skype for Business Server 2015 と共存できません。 アップグレードIn-Place実行した後、新しい LRS 管理 ツールをインストールします。 詳細については、「[Skype for Business Server 2015 の Microsoft Lync Room System 管理 Web ポータル](https://go.microsoft.com/fwlink/?LinkID=544807)」を参照してください。
  
2. アップグレードのプライマリ プール。
    
3. アーカイブ データベースと監視データベースをアップグレードするか、新しいデータベースを作成するか。
    
4. 使用するIn-Placeアップグレード方法:オフラインまたはユーザーの移動。 ユーザーの移動の一環として、プライマリ プールに関連付けられているグローバル会議ディレクトリも移行する必要があります。 
    
5. 影響を受けたユーザーの通信計画。
    
6. アップグレードが失敗した場合のバックアップ 計画。
    
アップグレード中にプライマリ プール内にいるユーザーは、アップグレードが完了するまでサービスを使用できません。 稼働しているセカンダリ プールがある場合は、アップグレード前にセカンダリ プールに移動することで、ユーザーへの影響を回避できます。 アップグレード後、ユーザーをプライマリ プールに戻します。
  
### <a name="in-place-upgrade-methods"></a>インプレース アップグレード方法

In-Placeアップグレードには、次の 2 つのシナリオがあります。 
  
- ユーザーのダウンタイムを必要としない Move User メソッド。 
    
- ダウンタイムが必要な Offline メソッド。
    
メンテナンス期間中にオフライン方式のアップグレードをスケジュールし、ダウンタイムがユーザーに通知されることをお勧めします。
  
> [!NOTE]
> Lync Server 2013 でペアになっているプールをアップグレードするときに、両方のプールを 2015 Skype for Business Serverにアップグレードする必要があります。 最初のプールをアップグレードした直後に、必ず 2 つ目のプールをアップグレードしてください。 1 つのプールが Lync Server 2013 を実行していて、2 つ目のプールが 2015 Skype for Business Server実行されている場合、ディザスター リカバリー オプションは最小限に抑えられます。 たとえば、1 つのプールが 2013 を実行していて、2 つ目が 2015 で障害が発生した場合、ペアになっているプールが同じバージョンでない場合、ディザスター モードではプール フェールオーバーがサポートされていないため、データが失われる可能性があります。 
  
#### <a name="in-place-upgrade-offline-method"></a>インプレース アップグレードオフライン方法

ユーザー プール間でユーザーを移動しない場合は、このメソッドを使用します。 アップグレード中、ユーザーは Lync または Skype for Business サービスを使用できなくなります。 
  
次の図は、このプロセスの概要を示しています。
  
![Lync 2013 ユーザーをオフラインにSkypeする。](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> プールがペアリングされている場合は、アップグレード前にペアリングを解除しないでください。 
  
サーバー プールのアップグレードを開始したら、プール全体のアップグレードを完了する必要があります。 Skype for Business Serverは、アップグレードされたプールの一部のみをサポートしていません。 
  
#### <a name="move-users-method-no-user-downtime"></a>ユーザーの移動方法 (ユーザーダウンタイムなし)
<a name="bkmk_MoveUsersMethod"> </a>

この方法を使用するには、アップグレードを開始する前にユーザーを別のプールに移動します。 アップグレード中、ユーザーは Lync サービスを使用できます。 アップグレードされたプールに移動したら、Skype for Businessを使用できます。 次の図は、このプロセスの概要を示しています。
  
> [!IMPORTANT]
> ユーザーの移動の一環として、プライマリ プールに関連付けられているグローバル会議ディレクトリも移行する必要があります。 PSTN ダイヤルイン会議では、ペアリングされたプールではなく、アップグレード中のプールに対して ConferenceID が解決されます。 そのため、アップグレード中にプールでスケジュールされた PSTN 会議に引き続きアクセスできるようにする場合は、会議ディレクトリを移動する必要があります。 
  
![プールがアップグレードされる前にユーザーが別のプールに移動され、アップグレード後にプールに戻されることを示すスイム ダイアグラム。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>ハードウェア のアップグレードのためにユーザーを移動する
<a name="bkmk_MoveUsersMethod"> </a>

 ハードウェアが [Skype for Business Server 2015 のサーバー要件を](requirements-for-your-environment/server-requirements.md)満たしていない場合は、新しい Skype for Business Server 2015 環境を設定し、ユーザーをそこに移動します。 次の図は、Lync Server 2010 からのアップグレードに関するこのプロセスの概要を示しています。 
  
![Lync Server プライマリ フロント エンド プールのユーザーが Skype for Business Server 2015 に移動され、Lync Server プールが使用停止になっていることを示すスイム レーン図。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>一括アップグレード プロセス

 次の手順を使用して、Lync Server 2013 から Skype for Business Server 2015 にアップグレードします。
  
1. アップグレード前にすべてのデータベースをバックアップします。
    
2. アップグレードするすべてのサービスが実行中の状態であることを確認します。
    
3. トポロジ ビルダーを使用してトポロジ ファイルをアップグレードして発行します。
    
4. すべてのフロントエンド サーバー上のすべてのサービスを停止します。
    
5. Skype for Business Serverに必要な新しい前提条件をインストールします。
    
6. 各フロントエンド サーバーで、In-Placeアップグレードを開始します。
    
7. アップグレードが完了したら、すべてのサービスを再起動します。
    
   - フロントエンド プールの場合は、Start-CsPool コマンドを使用してサービスを再起動します。
    
   - フロント エンド 以外のサーバーの場合は、Start-CSWindowsService を使用します。
    
> [!NOTE]
>  既存のアーカイブ データベースと監視データベースをアップグレードしない場合は、トポロジをアップグレードする前に依存関係を削除します。 新しいアーカイブ データベースと監視データベースを作成する場合は、アップグレード中に新しいSQL ストアを作成し、それをプールに関連付けることができます。 これを行う方法については、「[Skype for Business Server 2015 にアップグレードする](../deploy/upgrade-to-skype-for-business-server.md)」を参照してください。 インプレース アップグレード>、Skype for Business Serverの高可用性またはディザスター リカバリーはサポートされていません。 ユーザーのサービスを中断しないようにするには、 [ユーザーの移動方法 (ユーザーのダウンタイムなし)](upgrade.md#bkmk_MoveUsersMethod) を使用してアップグレードします。> アップグレード 処理中に、xds-replica はディスク ドライブ上のローカル共有フォルダーに配置され、空き領域が最も多くなります。 そのディスクが後で削除された場合は、サービスが起動しないなどの問題が発生する可能性があります。
  
### <a name="upgrade-order"></a>アップグレードの順序

トポロジを内部から外部にアップグレードします。 すべてのプールを最初にアップグレードし、次にエッジ サーバー、最後に中央管理Microsoft Store (CMS) プールをアップグレードします。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 認証に関する考慮事項

Web サービスに Kerberos 認証を使用する場合は、Kerberos アカウントを再割り当てし、In-Placeアップグレードが完了した後にパスワードをリセットする必要があります。 これを行う方法については、「 [Kerberos 認証のセットアップ」を](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-kerberos-authentication)参照してください。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Lync Server 2013 および Lync Server 2010 との共存のサポート
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

2015 Skype for Business Serverは、Lync Server 2013 または Lync Server 2010 と同じトポロジで実行できますが、3 つすべてを同じトポロジに含めることはできません。
  
Lync Server 2010 と Lync Server 2013 の間に共存している場合は、トポロジ全体を Lync Server 2013 にアップグレードしてから、In-Place アップグレードを使用して Skype for Business Server 2015 にアップグレードすることをお勧めします。 詳細については、「 [Lync Server 2010 から Lync Server 2013 への移行](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013)」を参照してください。
  
トポロジが主に Lync Server 2010 の場合は、トポロジを 2015 年 Skype for Business Serverにアップグレードする前に、Lync Server 2013 コンポーネントを Lync Server 2010 にロールバックします。 この場合、In-Place アップグレードの利点が失われ、Lync Server 2010 と Skype for Business Server 2015 の間に共存トポロジが存在します。
  
次の図は、Skype for Business Server 2015 と Lync Server 2013 および Lync Server 2010 の共存サポートを示しています。
  
![Lync Server 2013 または Lync Server 2010 とのSkype for Business Server 2015 の共存サポートを示す図。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>既存の存続可能ブランチ アプライアンスとサーバーを使用したアップグレード プロセス
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 では、存続可能ブランチ アプライアンス (SBA) または存続可能ブランチ サーバー (SBS) のIn-Placeアップグレードはサポートされていません。
  
ただし、Skype for Business Server データセンターと Lync Server 2010 または Lync Server 2013 SBA/SBS の共存はサポートされています。 
  
関連するブランチを使用して Lync Server 2013 フロントエンド (FE) プールのIn-Placeアップグレードを計画する場合は、既存のユーザーを Lync Server 2013 SBA/SBS に残すことができます。 アップグレード中、SBA/SBS ユーザーは回復モードになり、アップグレードが完了すると通常の機能に戻ります。 回復モードでのユーザーのエクスペリエンスの詳細については、 [Lync Server 2013 のブランチ サイトの回復機能に](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-features)関するページを参照してください。
  
Lync Server 2010 トポロジを 2015 Skype for Business Serverに移行する場合は、Lync Server 2013 への移行と同様に、SBA/SBS をトポロジに追加する必要があります。 必要な手順については、「 [Lync Server 2013 フロントエンド プールへの存続可能ブランチ アプライアンスの接続](/previous-versions/office/lync-server-2013/lync-server-2013-connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool)」を参照してください。
  
Lync Server 2010 と Lync Server 2013 の共存トポロジの場合は、「Lync Server 2013 および Lync Server 2010 との共存のサポート」セクションで行われた推奨事項に最初に合わせます。
  
## <a name="see-also"></a>関連項目
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Skype for Business Server 2015 にアップグレードする](../deploy/upgrade-to-skype-for-business-server.md)
  
[Skype for Business Server 2015 の環境要件](requirements-for-your-environment/environmental-requirements.md)
  
[Skype for Business Server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)
