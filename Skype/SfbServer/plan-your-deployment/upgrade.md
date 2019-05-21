---
title: Skype for Business Server 2015 へのアップグレードの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: '概要: Skype for Business Server 2015 へのアップグレードを計画するときに考慮する必要がある事項について説明します。 Skype for Business Server 2015 の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: 931ac609dec370d03fe50034300346b7e41c5f56
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296785"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Skype for Business Server 2015 へのアップグレードの計画
 
概要: Skype for Business Server 2015 へのアップグレードを計画するときに考慮する必要がある事項について説明します。 Skype for Business Server 2015 の無料トライアルは、次[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)の Microsoft 評価センターからダウンロードしてください。
  
Skype for business Server 2015 へのアップグレードの一環として、このトピックを使用して、Skype for Business Server 2015 への推奨アップグレードパス、インプレースアップグレードのしくみ、サポートされている共存シナリオの概要、アップグレードプロセスの概要について説明します。次のようになります。

> [!NOTE]
> インプレースアップグレードは、Skype for Business Server 2015 で使用できましたが、Skype for Business Server 2019 ではサポートされなくなりました。 サイドバイサイドの coexistance はサポートされています。詳細については、「 [Skype For Business Server 2019 への移行](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)」を参照してください。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Skype for Business Server 2015 への推奨されるアップグレードパス

 Lync Server 2013、Lync Server 2010、または Office Communications Server 2007 R2 から Skype for Business Server 2015 にアップグレードするには、次のアップグレードパスを使用します。
  
> [!CAUTION]
> 一括アップグレードを実行すると、Lync Server 2013 から Skype for Business Server 2015 に会議ディレクトリが自動的に移動されます。ただし、会議ディレクトリを手動で移動する場合は、必ず Skype for Business Server 2015 の管理シェルを使用してください。Lync Server 2013 管理シェルを使用して Lync Server 2013 から Skype for Business Server 2015 に会議ディレクトリを移動すると、データ損失が発生する可能性があります。一般に、Skype for Business Server 2015 を操作する場合は、その内容を問わず、Skype for Business Server 2015 ツール セットを使用する必要があります。  
  
|**バージョン**|**推奨される手順**|
|:-----|:-----|
|Lync Server 2013  <br/> | アップグレードするには、Skype for Business Server トポロジビルダーと、プールに関連付けられている各サーバー上の新しいインプレースアップグレード機能を使用します。 詳細な手順については、「 [Lync server 2013 から skype For Business server 2015 にアップグレード](upgrade.md#BKMK_PlanUpgradeFromLync2013)して skype For business [server 2015 に](../deploy/upgrade-to-skype-for-business-server.md)アップグレードする」を参照してください。 <br/> |
|Lync Server 2010 + Lync Server 2013 (デュアル モード)  <br/> |まず、Lync Server 2013 にアップグレードした後、新しいインプレースアップグレード機能を使用して、Skype for Business Server 2015 にアップグレードします。 ただし、トポロジが主に Lync Server 2010 である場合は、Lync Server 2013 コンポーネントを Lync Server 2010 にロールバックしてから、Skype for Business Server 2015 に直接アップグレードすることもできます。 この場合は、一括アップグレードを利用することはできず、Lync Server 2010 と Skype for Business Server 2015 の単純な共存を使用します。 3 つの共存はサポートされていませんが、2 つの共存はサポートされています。  <br/> |
|Lync Server 2010  <br/> |Skype for Business Server 2015 の新しいプールを表示してから、この新しいプールにユーザーを移行します。 その後、Lync Server 2010 の古いプールを使用停止することができます。 Lync Server 2010 から Skype for Business Server 2015 へのアップグレードは、Lync Server 2010 から Lync Server 2013 へのアップグレードに似ています。 「 [Lync server 2010 から Lync server 2013 への移行」を](https://go.microsoft.com/fwlink/p/?LinkId=526615)参照してください。  <br/> |
|Office Communications Server 2007 R2  <br/> | 次の 2 つのオプションのいずれかを選択します。 <br/>  新しい Skype for Business Server 2015 環境をセットアップします。 <br/>  または、ハードウェアとソフトウェアが Skype for Business Server 2015 の要件を満たしている場合は、Lync Server 2013 にアップグレードし、新しいインプレースアップグレード機能を使用して、Skype for Business Server 2015 にアップグレードします。 詳細については、「 [Skype For Business server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)」および「 [Office Communications server 2007 R2 から Lync server 2013 への移行](https://go.microsoft.com/fwlink/p/?LinkId=526616)」を参照してください。  <br/> |
   
> [!NOTE]
> SQL Server 2014 は、Skype for Business Server 2015 でサポートされていますが、Lync Server 2013 ではサポートされていません。 SQL Server 2012 から SQL Server 2014 にアップグレードする場合は、このドキュメントで説明されているインプレースアップグレード方法を使用して、プールを最初に Skype for Business Server 2015 にアップグレードする必要があります。 SQL Server 2012 から SQL Server 2014 にアップグレードするには、「 [Sql server 2014 にアップグレード](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx)する」を参照してください。 データベースの要件の詳細については、「 [Skype For Business server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)」を参照してください。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Lync Server 2013 から Skype for Business Server 2015 へのアップグレードの計画
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

新しいインプレースアップグレード機能を使用して、Lync Server 2013 システムを Skype for Business Server 2015 にアップグレードできます。 インプレースアップグレードでは、証明書のバックアップ、サーバーコンポーネントのアンインストール、ローカルデータベースのアップグレード、Skype for Business Server 2015 の役割のインストールを行うワンクリックソリューションが用意されています。 インプレースアップグレードでは、既存のハードウェアとサーバーの投資を維持し、Skype for Business Server 2015 の展開にかかる全体的なコストを削減します。
  
> [!NOTE]
> インプレースアップグレードでは、Skype for Business Server にアップグレードするときに同じハードウェアを使用することができます。 ただし、同じハードウェアを再利用しても、同じパフォーマンス容量には変換されません。 Lync Server 2013 と Skype for Business Server 2015 のパフォーマンスのロードが同じであると想定されることはありません。 
  
> [!NOTE]
> インプレースアップグレードでは、Skype for Business Server の高可用性または障害回復はサポートされません。 
  
インプレースアップグレードでは、Lync Server 2013 プールをオフラインにして、Skype for Business Server 2015 プールにアップグレードする必要があります。 
  
### <a name="create-an-in-place-upgrade-plan"></a>一括アップグレード計画の作成

次の内容を含む計画を作成します。
  
1. 現在のトポロジについて理解している。
    
    > [!NOTE]
    > インプレースアップグレードを実行する前に、必ず Lync Server 2013 用の LRS 管理ツールをアンインストールしてください。 Lync Server 2013 用の LRS 管理ツールは、Skype for Business Server 2015 と共存することはできません。 インプレースアップグレードを実行した後、新しい LRS 管理ツールをインストールします。詳細については、「 [Microsoft Lync Room System 管理 Web ポータル (Skype For Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) )」を参照してください。
  
2. アップグレードのプライマリプール。
    
3. アーカイブ データベースや監視データベースのアップグレードと、新しいデータベースの作成のどちらを選択するか。
    
4. 使用する一括アップグレードの方法: "オフライン" または "ユーザーの移動"。"ユーザーの移動" の一環としては、プライマリ プールと関連付けられているグローバルな会議ディレクトリも移行する必要があります。 
    
5. 影響を受けるユーザーの通信計画。
    
6. アップグレードが失敗した場合のバックアップ計画。
    
プライマリ プール内のユーザーは、そのプールのアップグレード中、完了するまでサービスを使用できません。 正しく機能するセカンダリ プールがある場合、アップグレードの前にユーザーをセカンダリ プールに移動することで、ユーザーに影響を与えることを回避できます。 アップグレード後、ユーザーをプライマリプールに戻します。
  
### <a name="in-place-upgrade-methods"></a>インプレース アップグレードの手法

一括アップグレードには次の 2 つのシナリオがあります。 
  
- ユーザーの移動という手法では、ユーザーのダウンタイムを必要としません。 
    
- オフラインという手法では、ダウンタイムを必要とします。
    
オフラインのアップグレードをメンテナンス ウィンドウ内にスケジュールして、ダウンタイムをユーザーに通知することが推奨されます。
  
> [!NOTE]
> Lync Server 2013 内にあるペアになったプールをアップグレードし、両方のプールを Skype for Business Server 2015 にアップグレードしようとする場合は、最初のプールをアップグレードした直後に、2 番目のプールも必ずアップグレードしてください。1 つのプールが Lync Server 2013 を実行しており、2 番目のプールが Skype for Business Server 2015 を実行している場合は、障害復旧オプションは最小化されます。たとえば、1 つのプールが 2013 を実行し、2 番目が 2015 を実行していて、障害が発生した場合は、データの損失が生じる恐れがあります。ペアになったプールが同じバージョンでない場合は、障害モードでプール フェールオーバーがサポートされていないためです。 
  
#### <a name="in-place-upgrade-offline-method"></a>インプレース アップグレードのオフラインの手法

ユーザーをユーザー プール間で移動したくない場合にこの方法を使用します。 アップグレード中は、ユーザーは Lync または Skype for Business サービスを使用できなくなります。 
  
次の図に、このプロセスの概要を示します。
  
![Lync 2013 からオフラインの Skype ユーザーへ](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> ペアになったプールがある場合、アップグレードの前にそれらのペアを解除しないでください。 
  
サーバー プールのアップグレードを開始した後、プール全体のアップグレードを完了する必要があります。 Skype for Business Server では、プールの一部のみがアップグレードされます。 
  
#### <a name="move-users-method-no-user-downtime"></a>ユーザーの移動の手法 (ユーザーのダウンタイムなし)
<a name="bkmk_MoveUsersMethod"> </a>

この手法を使用する場合、アップグレードを開始する前に、ユーザーを別のプールに移動します。 アップグレード中に、ユーザーは Lync services を使うことができます。 アップグレードされたプールに移動されると、Skype for Business を使用できるようになります。 次の図は、このプロセスの概要を示しています。
  
> [!IMPORTANT]
> "ユーザーの移動" の一環として、プライマリ プールと関連付けられているグローバルな会議ディレクトリも移行する必要があります。 PSTN ダイヤルイン会議では、依然として、ConferenceID を (ペアになっているプールではなく) アップグレードされているプールに解決します。 そのため、アップグレード中にプールでスケジュールされている PSTN 会議を引き続きアクセス可能にする場合は、会議ディレクトリを移動する必要があります。 
  
![プールのアップグレード前に別のプールに移動され、アップグレード後に元のプールに戻されるユーザーを示しているレーン図](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>ハードウェア アップグレードのためのユーザーの移動
<a name="bkmk_MoveUsersMethod"> </a>

 お使いのハードウェアが[skype For Business server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)を満たしていない場合は、新しい Skype For business server 2015 環境をセットアップし、ユーザーを移動します。 次の図に、Lync Server 2010 からアップグレードするためのこのプロセスの概要を示します。 
  
![Skype for Business Server 2015 に移動される Lync Server プライマリ フロントエンド プールおよび使用停止にする Lync Server プールにいるユーザーを示しているレーン図](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>インプレース アップグレードのプロセス

 Lync Server 2013 から Skype for Business Server 2015 にアップグレードするには、次の手順を実行します。
  
1. アップグレードの前に、すべてのデータベースをバックアップします。
    
2. アップグレードするすべてのサービスが実行状態にあることを確認します。
    
3. トポロジ ビルダーを使用して、トポロジ ファイルをアップグレードして公開します。
    
4. すべてのフロントエンド サーバーのすべてのサービスを停止します。
    
5. Skype for Business Server に必要な新しい前提条件をインストールします。
    
6. 各フロントエンド サーバーで、一括アップグレードを開始します。
    
7. アップグレードが完了したら、すべてのサービスを再起動します。
    
   - フロントエンド プールについては、コマンド Start-CsPool を使用してサービスを再起動します。
    
   - フロントエンド サーバー以外については、Start-CSWindowsService を使用します。
    
> [!NOTE]
>  既存のアーカイブおよび監視データベースをアップグレードしない場合は、トポロジをアップグレードする前に、依存関係を削除します。 アップグレード中に新しいアーカイブおよび監視データベースを作成する場合は、新しい SQL ストアを作成して、それをプールに関連付けます。 手順については、「[Skype for Business Server 2015 にアップグレード](../deploy/upgrade-to-skype-for-business-server.md)する」を参照してください。 > のインプレースアップグレードでは、Skype for Business Server の高可用性または障害回復はサポートされません。 ユーザーのサービスが中断されないようにするには、[[ユーザーの移動] メソッド (ユーザーのダウンタイムは不要)](upgrade.md#bkmk_MoveUsersMethod)を使用して、アップグレードプロセス中に > を使います。このファイルは、ディスクドライブ上のローカル共有フォルダーに、最も空き領域があるローカル共有フォルダーに配置されます。 そのディスクが後で取り外されると、サービスが開始されないなどの問題が発生することがあります。
  
### <a name="upgrade-order"></a>アップグレードの順序

トポロジを内側から外側にアップグレードします。 最初にすべてのプール、続いてエッジ サーバーをアップグレードして、最後に中央管理ストア (CMS) プールをアップグレードします。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 認証に関する考慮事項

Web サービスに Kerberos 認証を使用する場合は、一括アップグレードの完了後に、Kerberos アカウントを再割り当てしてパスワードをリセットする必要があります。 この方法については、「 [Kerberos 認証を設定](https://go.microsoft.com/fwlink/p/?LinkId=530342)する」を参照してください。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Lync Server 2013 および Lync Server 2010 との共存のサポート
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 は、Lync Server 2013 または Lync Server 2010 と同じトポロジで実行することができますが、3 つすべてを同じトポロジにすることはできません。
  
Lync Server 2010 と Lync Server 2013 が共存する場合は、トポロジ全体を Lync Server 2013 にアップグレードしてから、一括アップグレードを使用して Skype for Business Server 2015 にアップグレードすることをお勧めします。 詳細については、「 [Lync server 2010 から Lync server 2013 に移行する](https://go.microsoft.com/fwlink/p/?LinkId=526615)」を参照してください。
  
使用するトポロジがおもに Lync Server 2010 である場合は、トポロジを Skype for Business Server 2015 にアップグレードする前に、Lync Server 2013 コンポーネントを Lync Server 2010 にロールバックします。その場合は、一括アップグレードを利用するメリットや、Lync Server 2010 と Skype for Business Server 2015 間でトポロジを共存させるメリットが得られません。
  
次の図は、Skype for Business Server 2015 と Lync Server 2013 および Lync Server 2010 の共存サポートを示しています。
  
![Lync Server 2013 または Lync Server 2010 との Skype for Business Server 2015 の共存のサポートを示している図](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>既存の存続可能ブランチ アプライアンスおよびサーバーを使用したアップグレード プロセス
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 は、Survivable Branch Appliance (SBA) または Survivable Branch Server (SBS) のインプレースアップグレードをサポートしていません。
  
ただし、Skype for Business Server データセンターと Lync Server 2010 または Lync Server 2013 SBA/SBS の共存はサポートしています。 
  
Lync Server 2013 Front End (FE) プールとそれに関連付けられたブランチの一括アップグレードを計画する場合、Lync Server 2013 SBA/SBS の既存ユーザーは残すことができます。 アップグレード中、SBA/SBS ユーザーは復元モードになり、アップグレードが完了すると通常の機能に戻ります。 回復性モードでのユーザーエクスペリエンスの詳細については、「 [Lync Server 2013 のブランチサイトの回復機能](https://technet.microsoft.com/library/gg398715.aspx)」を参照してください。
  
Lync Server 2010 トポロジを Skype for Business Server 2015 に移行する場合は、Lync Server 2013 への移行と同様に、SBA/SBS をトポロジにもう一度追加する必要があります。 必要な手順については、「Survivable Branch Appliance の接続」2013を参照してください。
  
Lync Server 2010 および Lync Server 2013 の共存するトポロジについては、まず「Lync Server 2013 および Lync Server 2010 を使用した共存のサポート」に記載されている推奨事項に合わせてください。
  
## <a name="see-also"></a>関連項目
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Skype for Business Server 2015 へのアップグレード](../deploy/upgrade-to-skype-for-business-server.md)
  
[Environmental requirements for Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
