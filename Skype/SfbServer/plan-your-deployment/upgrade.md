---
title: Skype for Business Server 2015 へのアップグレードを計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server 2015 へのアップグレードを計画するときに考慮する必要のある事柄について説明します。 Microsoft 評価センター () から、Skype for Business Server 2015 の無料試用版をhttps://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverダウンロードしてください。'
ms.openlocfilehash: 91cc78f22c03bf7ec59c9ac0c936f194ece71a35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030641"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Skype for Business Server 2015 へのアップグレードを計画する
 
概要: Skype for Business Server 2015 へのアップグレードを計画するときに考慮する必要のある事柄について説明します。 Microsoft 評価センター () から、Skype for Business Server 2015 の無料試用版を[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)ダウンロードしてください。
  
Skype for business Server 2015 へのアップグレード計画の一環として、このトピックを使用して、Skype for business Server 2015 への推奨されるアップグレードパス、インプレースアップグレードのしくみ、サポートされている共存シナリオ、およびアップグレードプロセスについて理解します。は次のようになります。

> [!NOTE]
> 一括アップグレードは Skype for business Server 2015 で利用できましたが、Skype for Business Server 2019 ではサポートされなくなりました。 詳細については、「 [Skype for Business Server 2019 の移行](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)」を参照してください。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Skype for Business Server 2015 への推奨されるアップグレードパス

 Lync Server 2013、Lync Server 2010、または Office Communications Server 2007 R2 から Skype for Business Server 2015 にアップグレードするには、次のアップグレードパスを使用します。
  
> [!CAUTION]
> 一括アップグレードでは、会議ディレクトリが Lync Server 2013 から Skype for Business Server 2015 に自動的に移動されます。 ただし、会議ディレクトリを手動で移動する予定の場合は、Skype for Business Server 2015 管理シェルを使用することが非常に重要です。 Lync server 2013 管理シェルを使用して、会議ディレクトリを Lync Server 2013 から Skype for Business Server 2015 に移動しようとすると、データが失われる可能性があります。 一般に、すべての容量で Skype for business Server 2015 を使用している場合は常に、Skype for Business Server 2015 ツールセットを使用する必要があります。  
  
|**バージョン**|**推奨**|
|:-----|:-----|
|Lync Server 2013  <br/> | アップグレードするには、そのプールに関連付けられている各サーバーで Skype for Business Server トポロジビルダーと新しい一括アップグレード機能を使用します。 詳細な手順については、「 [Plan to upgrade To Lync server 2013 To skype for Business server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) 」および「skype For business [server 2015 へのアップグレード](../deploy/upgrade-to-skype-for-business-server.md)」を参照してください。 <br/> |
|Lync Server 2010 + Lync Server 2013 (デュアルモード)  <br/> |最初に、Lync Server 2013 にアップグレードしてから、新しい一括アップグレード機能を使用して Skype for Business Server 2015 にアップグレードします。 ただし、トポロジがプライマリ Lync Server 2010 の場合は、lync server 2013 コンポーネントを Lync Server 2010 にロールバックしてから、Skype for Business Server 2015 に直接アップグレードすることもできます。 この場合、一括アップグレードを利用することはできません。 Lync Server 2010 と Skype for Business Server 2015 の間で純粋な共存が使用されます。 3次元存在はサポートされていませんが、共存がサポートされています。  <br/> |
|Lync Server 2010  <br/> |新しい Skype for Business Server 2015 プールを起動し、ユーザーをこの新しいプールに移行します。 その後、古い Lync Server 2010 プールを使用停止にすることができます。 Lync server 2010 から Skype for Business Server 2015 へのアップグレードは、Lync Server 2010 から Lync Server 2013 へのアップグレードに似ています。 「 [Lync server 2010 から Lync server 2013 への移行」を](https://go.microsoft.com/fwlink/p/?LinkId=526615)参照してください。  <br/> |
|Office Communications Server 2007 R2  <br/> | 次の2つのオプションのいずれかを選択します。 <br/>  新しい Skype for Business Server 2015 環境をセットアップします。 <br/>  または、ハードウェアとソフトウェアが Skype for Business Server 2015 の要件を満たしている場合は、Lync Server 2013 にアップグレードしてから、新しい一括アップグレード機能を使用して Skype for Business Server 2015 にアップグレードします。 詳細については、「 [Skype For Business server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)」および「 [Office Communications server 2007 R2 から Lync Server 2013 への移行](https://go.microsoft.com/fwlink/p/?LinkId=526616)」を参照してください。  <br/> |
   
> [!NOTE]
> SQL Server 2014 は Skype for Business Server 2015 でサポートされていますが、Lync Server 2013 ではサポートされていません。 SQL Server 2012 から SQL Server 2014 にアップグレードする場合は、このドキュメントで説明されているように、一括アップグレード方法を使用して、最初にプールを Skype for Business Server 2015 にアップグレードする必要があります。 その後、sql Server 2012 から SQL Server 2014 にアップグレードできます。詳細については、「 [upgrade TO Sql server 2014](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx)」を参照してください。 データベース要件の詳細については、「 [Skype For Business server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)」を参照してください。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Lync Server 2013 から Skype for Business Server 2015 へのアップグレードを計画する
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

新しい一括アップグレード機能を使用して、Lync Server 2013 システムを Skype for Business Server 2015 にアップグレードできます。 一括アップグレードには、証明書をバックアップし、サーバーコンポーネントをアンインストールし、ローカルデータベースをアップグレードし、Skype for Business Server 2015 の役割をインストールするワンクリックソリューションが用意されています。 一括アップグレードでは、既存のハードウェアとサーバーへの投資を維持するために、Skype for Business Server 2015 を展開するための全体的なコストが削減されます。
  
> [!NOTE]
> 一括アップグレードでは、Skype for Business Server へのアップグレード時に同じハードウェアを使用することができます。 ただし、同じハードウェアを再利用しても、同じパフォーマンス容量には変換されません。 Lync Server 2013 と Skype for Business Server 2015 では、パフォーマンスの負荷が同一であるとは予想されません。 
  
> [!NOTE]
> 一括アップグレードでは、Skype for Business Server の高可用性または障害復旧はサポートされません。 
  
一括アップグレードでは、Lync Server 2013 プールをオフラインにして Skype for Business Server 2015 プールにアップグレードする必要があります。 
  
### <a name="create-an-in-place-upgrade-plan"></a>一括アップグレード計画を作成する

以下を含むプランを作成します。
  
1. 現在のトポロジについて理解します。
    
    > [!NOTE]
    > 一括アップグレードを実行する前に、必ず Lync Server 2013 の LRS 管理ツールをアンインストールしてください。 Lync Server 2013 の LRS 管理ツールを Skype for Business Server 2015 と共存させることはできません。 一括アップグレードを実行した後、新しい LRS 管理ツールをインストールします。 詳細については、「 [Microsoft Lync Room System 管理 Web Portal For Skype For Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) 」を参照してください。
  
2. アップグレードのプライマリプール。
    
3. アーカイブデータベースと監視データベースをアップグレードするか、新しいデータベースを作成するか。
    
4. 一括アップグレード方法: オフラインまたはユーザーの移動を使用します。 ユーザーの移動の一環として、プライマリプールに関連付けられているグローバル会議ディレクトリも移行する必要があります。 
    
5. 影響を受けるユーザーのためのコミュニケーション計画。
    
6. アップグレードが失敗した場合のバックアップ計画。
    
アップグレード中のプライマリプールのユーザーは、アップグレードが完了するまでサービスを使用できません。 セカンダリプールが稼働している場合は、アップグレードの前にユーザーをセカンダリプールに移動することによって、そのユーザーに影響を与えることを避けることができます。 アップグレードの後、ユーザーをプライマリプールに戻します。
  
### <a name="in-place-upgrade-methods"></a>一括アップグレードの方法

一括アップグレードには、次の2つのシナリオがあります。 
  
- ユーザーにダウンタイムを発生させないようにユーザーを移動する方法。 
    
- オフライン方法。ダウンタイムが必要です。
    
メンテナンス期間中にオフラインの方法でのアップグレードをスケジュールし、ユーザーにダウンタイムが通知されるようにすることをお勧めします。
  
> [!NOTE]
> Lync Server 2013 でペアになっているプールをアップグレードするときに、両方のプールを Skype for Business Server 2015 にアップグレードする場合。 最初のプールをアップグレードした直後に、2番目のプールをすぐにアップグレードしてください。 あるプールが Lync Server 2013 を実行していて、2番目のプールで Skype for Business Server 2015 が実行されている場合は、障害復旧オプションが最小化されます。 たとえば、1つのプールが2013を実行している場合に、2番目のプールが2015、障害が発生した場合、プールのフェールオーバーは、ペアのプールが同じバージョンでないと、障害モードではサポートされないため、データ損失が発生する可能性があります。 
  
#### <a name="in-place-upgrade-offline-method"></a>一括アップグレードのオフライン方法

ユーザープール間でユーザーを移動しない場合は、この方法を使用します。 アップグレード中、ユーザーは Lync または Skype for Business サービスを使用できません。 
  
次の図は、このプロセスの概要を示しています。
  
![Lync 2013 から Skype ユーザーへのオフライン](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> プールがペアになっている場合は、アップグレードの前に解除を実行しないでください。 
  
サーバープールのアップグレードを開始したら、プール全体のアップグレードを完了する必要があります。 Skype for Business Server は、プールの一部のみをアップグレードすることをサポートしていません。 
  
#### <a name="move-users-method-no-user-downtime"></a>ユーザーの移動方法 (ユーザーのダウンタイムなし)
<a name="bkmk_MoveUsersMethod"> </a>

この方法を使用するには、アップグレードを開始する前に、ユーザーを別のプールに移動します。 アップグレード中、ユーザーは Lync services を使用できます。 アップグレードされたプールに移動されると、Skype for Business を使用できるようになります。 次の図は、このプロセスの概要を示しています。
  
> [!IMPORTANT]
> ユーザーの移動の一環として、プライマリプールに関連付けられているグローバル会議ディレクトリも移行する必要があります。 PSTN ダイヤルイン会議では、ConferenceID は、ペアになっているプールではなく、アップグレードされているプールに対して引き続き解決されます。 そのため、アップグレード中にプールでスケジュールされた PSTN 会議にアクセスできるようにするには、会議ディレクトリを移動する必要があります。 
  
![プールがアップグレードされ、アップグレード後にプールに戻される前に、別のプールに移動されるユーザーを示すスイムダイアグラム。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>ハードウェアアップグレードのためにユーザーを移動する
<a name="bkmk_MoveUsersMethod"> </a>

 使用しているハードウェアが[skype for Business server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)を満たしていない場合は、新しい Skype For business server 2015 環境をセットアップし、ユーザーをそこに移動します。 次の図は、Lync Server 2010 からのアップグレードに関するこのプロセスの概要を示しています。 
  
![Skype for Business Server 2015 および Lync Server プールを使用停止に移行する Lync Server プライマリフロントエンドプール内のユーザーを示すスイムレーン図。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>一括アップグレード プロセス

 次の手順を使用して、Lync Server 2013 から Skype for Business Server 2015 にアップグレードします。
  
1. アップグレードの前にすべてのデータベースをバックアップします。
    
2. アップグレードするすべてのサービスが実行中の状態であることを確認します。
    
3. トポロジビルダーを使用して、トポロジファイルをアップグレードして公開します。
    
4. すべてのフロントエンドサーバー上のすべてのサービスを停止します。
    
5. Skype for Business Server に必要な新しい必須コンポーネントをインストールします。
    
6. 各フロントエンドサーバーで、一括アップグレードを開始します。
    
7. アップグレードが完了したら、すべてのサービスを再起動します。
    
   - フロントエンドプールの場合は、コマンドの Start-CsPool を使用してサービスを再起動します。
    
   - フロントエンドサーバー以外の場合は、Start-CSWindowsService を使用します。
    
> [!NOTE]
>  既存のアーカイブデータベースと監視データベースをアップグレードしない場合は、トポロジをアップグレードする前に依存関係を削除してください。 新しいアーカイブデータベースと監視データベースを作成する場合は、アップグレード中に新しい SQL ストアを作成し、それをプールに関連付けることができます。 この方法の手順については、「[Skype For Business Server 2015 へのアップグレード](../deploy/upgrade-to-skype-for-business-server.md)」を参照してください。 > 一括アップグレードでは、Skype for Business Server の高可用性または障害復旧をサポートしていません。 ユーザーのサービスが中断されないようにするには、「ユーザーを移動する」の[方法 (ユーザーのダウンタイムなし)](upgrade.md#bkmk_MoveUsersMethod)を使用してアップグレードを行います。 > は、アップグレードプロセス中に、最大空き容量があるディスクドライブ上のローカル共有フォルダーに xds-レプリカを配置します。 そのディスクが後で削除されると、サービスが開始されないなどの問題が発生する可能性があります。
  
### <a name="upgrade-order"></a>アップグレードの順序

内部から外部にトポロジをアップグレードします。 最初にすべてのプール、次にエッジサーバー、最後に中央管理ストア (CMS) プールをアップグレードします。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 認証に関する考慮事項

Web サービスで Kerberos 認証を使用する場合は、一括アップグレードの完了後に Kerberos アカウントを再割り当てし、パスワードをリセットする必要があります。 これを行う方法については、「 [Kerberos 認証の設定](https://go.microsoft.com/fwlink/p/?LinkId=530342)」を参照してください。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Lync Server 2013 および Lync Server 2010 との共存のサポート
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 は、Lync Server 2013 または Lync Server 2010 と同じトポロジで実行できますが、3つすべてを同じトポロジで使用することはできません。
  
Lync Server 2010 と Lync Server 2013 の間に共存がある場合は、トポロジ全体を Lync Server 2013 にアップグレードしてから、一括アップグレードを使用して Skype for Business Server 2015 にアップグレードすることをお勧めします。 詳細については、「 [Lync server 2010 から Lync server 2013 への移行](https://go.microsoft.com/fwlink/p/?LinkId=526615)」を参照してください。
  
トポロジが主に Lync Server 2010 の場合は、トポロジを Skype for Business Server 2015 にアップグレードする前に、lync server 2013 コンポーネントを Lync Server 2010 にロールバックします。 この場合、インプレースアップグレードのメリットは失われ、Lync Server 2010 と Skype for Business Server 2015 の間に共存するトポロジがあります。
  
次の図は、Lync Server 2013 および Lync Server 2010 との Skype for Business Server 2015 の共存のサポートを示しています。
  
![Lync Server 2013 または Lync Server 2010 での Skype for Business Server 2015 の共存のサポートを示す図。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>既存の存続可能ブランチアプライアンスとサーバーを使用したアップグレードプロセス
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 は、存続可能 Branch Appliance (SBA) または存続可能ブランチサーバー (SBS) の一括アップグレードをサポートしていません。
  
ただし、Skype for Business Server データセンターと Lync server 2010 または Lync Server 2013 SBA/SBS の共存はサポートされています。 
  
関連付けられたブランチを使用して Lync Server 2013 フロントエンド (FE) プールの一括アップグレードを計画する場合は、Lync Server 2013 SBA/SBS の既存のユーザーのままにしておくことができます。 アップグレード中に、SBA/SBS ユーザーは復元モードになり、アップグレードが完了した後、通常の機能に戻ります。 復元モード中のユーザーの作業の詳細については、「 [Lync Server 2013 の「ブランチサイトの復元機能](https://technet.microsoft.com/library/gg398715.aspx)」を参照してください。
  
Lync server 2010 トポロジを Skype for Business Server 2015 に移行する場合は、Lync Server 2013 への移行と同様に、SBA/SBS をトポロジに再追加する必要があります。 必要な手順については、「[接続存続可能 Branch Appliance から Lync Server 2013 フロントエンドプールへの接続](https://technet.microsoft.com/library/jj688026.aspx)」を参照してください。
  
Lync Server 2010 および Lync Server 2013 の併置されたトポロジについては、最初に「Lync Server 2013 および Lync Server 2010 との共存のサポート」のセクションで説明されている推奨事項に合わせます。
  
## <a name="see-also"></a>関連項目
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Skype for Business Server 2015 へのアップグレード](../deploy/upgrade-to-skype-for-business-server.md)
  
[Skype for Business Server 2015 の環境要件](requirements-for-your-environment/environmental-requirements.md)
  
[Skype for Business Server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)
