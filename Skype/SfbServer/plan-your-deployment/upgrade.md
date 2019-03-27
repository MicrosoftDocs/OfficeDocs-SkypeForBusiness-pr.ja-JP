---
title: Skype for Business Server 2015 へのアップグレードの計画
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: '概要: は、ビジネス サーバー 2015 の Skype へのアップグレードを計画する場合を考慮する必要がある事項について説明します。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 711b675c902824e6aab31ed64266a946a135b7fb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899166"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Skype for Business Server 2015 へのアップグレードの計画
 
概要: は、ビジネス サーバー 2015 の Skype へのアップグレードを計画する場合を考慮する必要がある事項について説明します。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
ビジネス サーバー 2015 Skype にアップグレードする計画の一環として、どのようにビジネス サーバー 2015 年の Skype に推奨されるアップグレード パスを理解するこのトピックを使用して、埋め込みのアップグレードは、サポートされる共存シナリオとは、どのようなアップグレード ・ プロセス次のようにします。

> [!NOTE]
> インプレース アップグレードはビジネス サーバー 2015 の Skype で利用できるが、ビジネス サーバー 2019 の Skype でサポートされていません。 Coexistance のサポートに並べて、[ビジネス サーバー 2019 の Skype への移行](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)の詳細についてを参照してください。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype に推奨されるアップグレード ・ パス

 ビジネス サーバー 2015 の Skype Lync Server 2013、Lync Server 2010 の場合、または通信サーバー 2007 R2 の Office からアップグレードするには、次のアップグレード パスを使用します。
  
> [!CAUTION]
> 一括アップグレードを実行すると、Lync Server 2013 から Skype for Business Server 2015 に会議ディレクトリが自動的に移動されます。ただし、会議ディレクトリを手動で移動する場合は、必ず Skype for Business Server 2015 の管理シェルを使用してください。Lync Server 2013 管理シェルを使用して Lync Server 2013 から Skype for Business Server 2015 に会議ディレクトリを移動すると、データ損失が発生する可能性があります。一般に、Skype for Business Server 2015 を操作する場合は、その内容を問わず、Skype for Business Server 2015 ツール セットを使用する必要があります。  
  
|**バージョン**|**推奨される手順**|
|:-----|:-----|
|Lync Server 2013  <br/> | アップグレードするには、ビジネス サーバー トポロジ ビルダーおよび各プールに関連付けられているサーバーのインプレース アップグレードの新機能、Skype を使用します。 詳細な手順については、[ビジネス サーバー 2015 の Skype に Lync Server 2013 からのアップグレードを計画](upgrade.md#BKMK_PlanUpgradeFromLync2013)し、[ビジネス サーバー 2015 の Skype へのアップグレード](../deploy/upgrade-to-skype-for-business-server.md)を参照してください。 <br/> |
|Lync Server 2010 + Lync Server 2013 (デュアル モード)  <br/> |まず、Lync Server 2013 にアップグレードし、アップグレード Skype をビジネス サーバー 2015 のインプレース アップグレードの新機能を使用しています。 ただし、トポロジが主に Lync Server 2010 である場合は、Lync Server 2013 コンポーネントを Lync Server 2010 にロールバックしてから、Skype for Business Server 2015 に直接アップグレードすることもできます。 この場合は、一括アップグレードを利用することはできず、Lync Server 2010 と Skype for Business Server 2015 の単純な共存を使用します。 3 つの共存はサポートされていませんが、2 つの共存はサポートされています。  <br/> |
|Lync Server 2010  <br/> |Skype for Business Server 2015 の新しいプールを表示してから、この新しいプールにユーザーを移行します。 その後、Lync Server 2010 の古いプールを使用停止することができます。 Lync Server 2010 から Skype for Business Server 2015 へのアップグレードは、Lync Server 2010 から Lync Server 2013 へのアップグレードに似ています。 [Lync Server 2013 に Lync Server 2010 の移行](https://go.microsoft.com/fwlink/p/?LinkId=526615)を参照してください。  <br/> |
|Office Communications Server 2007 R2  <br/> | 次の 2 つのオプションのいずれかを選択します。 <br/>  サーバー 2015 のビジネス環境の新しい Skype を設定します。 <br/>  または、ハードウェアとソフトウェアがビジネス サーバー 2015 の Skype の要件を満たしている場合に Lync Server 2013 では、アップグレードし、アップグレード Skype をビジネス サーバー 2015 のインプレース アップグレードの新機能を使用しています。 詳細については、[ビジネス サーバー 2015 の Skype のサーバー要件](requirements-for-your-environment/server-requirements.md)と[Lync Server 2013 への Office 通信 Server 2007 R2 からの移行](https://go.microsoft.com/fwlink/p/?LinkId=526616)を参照してください。  <br/> |
   
> [!NOTE]
> SQL Server 2014 はビジネス サーバー 2015 の Skype ではサポートされていますが、Lync Server 2013 でサポートされていません。 2014 の SQL Server を SQL Server 2012 にアップグレードする場合は、プールする必要がありますまずアップグレードする Skype をビジネス サーバー 2015 の埋め込みのアップグレード方法を使用してこのドキュメントで説明したように。 アップグレードすることができますし、2014 の SQL Server に SQL Server 2012 から[2014 の SQL Server へのアップグレード](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx)を参照してください。 データベースの要件に関する詳細については、[ビジネス サーバー 2015 の Skype のサーバーの要件](requirements-for-your-environment/server-requirements.md)を参照してください。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Lync Server 2013 から Skype for Business Server 2015 へのアップグレードの計画
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype に Lync Server 2013 のシステムをアップグレードするには、インプレース アップグレードの新機能を使用して、ビジネス サーバー 2015 のです。 インプレース アップグレードには、証明書をバックアップし、サーバー コンポーネントをアンインストールする、ローカルのデータベースをアップグレード サーバー 2015 のビジネス ロールの Skype をインストール 1 回のクリック解決策が用意されています。 インプレース アップグレードは、既存のハードウェアおよび全体的なビジネス サーバー 2015 Skype を導入するコストを削減、サーバへの投資を保持するために目指しています。
  
> [!NOTE]
> インプレース アップグレードを使用すると、Skype をビジネス サーバーをアップグレードする場合は、同じハードウェアを使用します。 ただし、同じハードウェアを再利用することはパフォーマンス容量が同じには変換されません。 パフォーマンスの負荷と同じにするには、Lync Server 2013 とビジネス サーバー 2015 の Skype をすることはありません。 
  
> [!NOTE]
> インプレース アップグレードは高可用性、災害復旧をビジネス サーバーの Skype はサポートされていません。 
  
インプレース アップグレードでは、Lync Server 2013 プールをオフラインにして、Skype ビジネス サーバー 2015 プール用にアップグレードする必要があります。 
  
### <a name="create-an-in-place-upgrade-plan"></a>一括アップグレード計画の作成

次の内容を含む計画を作成します。
  
1. 現在のトポロジを理解します。
    
    > [!NOTE]
    > インプレース アップグレードを実行する前に Lync Server 2013 の LRS の管理ツールをアンインストールすることを確認します。 Lync Server 2013 の LRS の管理ツールは、ビジネス サーバー 2015 の Skype と共存できません。 新しい LRS の管理ツールのインストールのインプレース アップグレードを実行した後、 [Microsoft Lync ルーム システム管理用 Web ポータル ビジネス サーバー 2015 の Skype](https://go.microsoft.com/fwlink/?LinkID=544807)を参照してください。
  
2. アップグレードの主なプールです。
    
3. アーカイブ データベースや監視データベースのアップグレードと、新しいデータベースの作成のどちらを選択するか。
    
4. 使用する一括アップグレードの方法: "オフライン" または "ユーザーの移動"。"ユーザーの移動" の一環としては、プライマリ プールと関連付けられているグローバルな会議ディレクトリも移行する必要があります。 
    
5. 影響を受けるユーザーの通信計画。
    
6. アップグレードが失敗した場合のバックアップ計画。
    
プライマリ プール内のユーザーは、そのプールのアップグレード中、完了するまでサービスを使用できません。 正しく機能するセカンダリ プールがある場合、アップグレードの前にユーザーをセカンダリ プールに移動することで、ユーザーに影響を与えることを回避できます。 アップグレード後、ユーザーをプライマリ プールに戻る移動します。
  
### <a name="in-place-upgrade-methods"></a>インプレース アップグレードの手法

一括アップグレードには次の 2 つのシナリオがあります。 
  
- ユーザーの移動という手法では、ユーザーのダウンタイムを必要としません。 
    
- オフラインという手法では、ダウンタイムを必要とします。
    
オフラインのアップグレードをメンテナンス ウィンドウ内にスケジュールして、ダウンタイムをユーザーに通知することが推奨されます。
  
> [!NOTE]
> Lync Server 2013 内にあるペアになったプールをアップグレードし、両方のプールを Skype for Business Server 2015 にアップグレードしようとする場合は、最初のプールをアップグレードした直後に、2 番目のプールも必ずアップグレードしてください。1 つのプールが Lync Server 2013 を実行しており、2 番目のプールが Skype for Business Server 2015 を実行している場合は、障害復旧オプションは最小化されます。たとえば、1 つのプールが 2013 を実行し、2 番目が 2015 を実行していて、障害が発生した場合は、データの損失が生じる恐れがあります。ペアになったプールが同じバージョンでない場合は、障害モードでプール フェールオーバーがサポートされていないためです。 
  
#### <a name="in-place-upgrade-offline-method"></a>インプレース アップグレードのオフラインの手法

ユーザーをユーザー プール間で移動したくない場合にこの方法を使用します。 アップグレード中にユーザーはビジネス ・ サービスの Lync または Skype を使用することできません。 
  
次の図に、このプロセスの概要を示します。
  
![Lync 2013 からオフラインの Skype ユーザーへ](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> ペアになったプールがある場合、アップグレードの前にそれらのペアを解除しないでください。 
  
サーバー プールのアップグレードを開始した後、プール全体のアップグレードを完了する必要があります。 Skype ビジネス サーバーは、プールのアップグレードの一部のみをサポートしていません。 
  
#### <a name="move-users-method-no-user-downtime"></a>ユーザーの移動の手法 (ユーザーのダウンタイムなし)
<a name="bkmk_MoveUsersMethod"> </a>

この手法を使用する場合、アップグレードを開始する前に、ユーザーを別のプールに移動します。 アップグレード中のユーザーは、Lync サービスを使用できます。 アップグレードされたプールに移動して、ビジネスの Skype を使用できます。 次の図は、このプロセスの概要を示しています。
  
> [!IMPORTANT]
> "ユーザーの移動" の一環として、プライマリ プールと関連付けられているグローバルな会議ディレクトリも移行する必要があります。 PSTN ダイヤルイン会議では、依然として、ConferenceID を (ペアになっているプールではなく) アップグレードされているプールに解決します。 そのため、アップグレード中にプールでスケジュールされている PSTN 会議を引き続きアクセス可能にする場合は、会議ディレクトリを移動する必要があります。 
  
![プールのアップグレード前に別のプールに移動され、アップグレード後に元のプールに戻されるユーザーを示しているレーン図](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>ハードウェア アップグレードのためのユーザーの移動
<a name="bkmk_MoveUsersMethod"> </a>

 [ビジネス サーバー 2015 の Skype のサーバーの要件](requirements-for-your-environment/server-requirements.md)を満たしていないのは、ハードウェア場合、は、サーバー 2015 のビジネス環境、新しい Skype をセットアップし、あるユーザーを移動します。 次の図に、Lync Server 2010 からアップグレードするためのこのプロセスの概要を示します。 
  
![Skype for Business Server 2015 に移動される Lync Server プライマリ フロントエンド プールおよび使用停止にする Lync Server プールにいるユーザーを示しているレーン図](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>インプレース アップグレードのプロセス

 次の手順を使用して、ビジネス サーバー 2015 の Lync Server 2013 を Skype にアップグレードします。
  
1. アップグレードの前に、すべてのデータベースをバックアップします。
    
2. アップグレードするすべてのサービスが実行状態にあることを確認します。
    
3. トポロジ ビルダーを使用して、トポロジ ファイルをアップグレードして公開します。
    
4. すべてのフロントエンド サーバーのすべてのサービスを停止します。
    
5. Skype に必要なビジネス サーバーの新しいの前提条件をインストールします。
    
6. 各フロントエンド サーバーで、一括アップグレードを開始します。
    
7. アップグレードが完了したら、すべてのサービスを再起動します。
    
   - フロントエンド プールについては、コマンド Start-CsPool を使用してサービスを再起動します。
    
   - フロントエンド サーバー以外については、Start-CSWindowsService を使用します。
    
> [!NOTE]
>  既存のアーカイブおよび監視データベースをアップグレードしない場合は、トポロジをアップグレードする前に、依存関係を削除します。 アップグレード中に新しいアーカイブおよび監視データベースを作成する場合は、新しい SQL ストアを作成して、それをプールに関連付けます。 [ビジネス サーバー 2015 の Skype へのアップグレード](../deploy/upgrade-to-skype-for-business-server.md)のトピックでこれを行う方法の手順が表示されます。 _gt インプレース アップグレードがサポートされていませんの高可用性/災害復旧 Skype のビジネス サーバーの。 ユーザーのサービスを中断することを避けるため、xds のレプリカは、最も空き領域を持つディスク ドライブ上のローカルの共有フォルダーに配置されます、アップグレード処理中に upgrade.> には、[ユーザーの移動方法 (ユーザーのダウンタイムなし)](upgrade.md#bkmk_MoveUsersMethod)を使用します。 そのディスクが後で取り外されると、サービスが開始されないなどの問題が発生することがあります。
  
### <a name="upgrade-order"></a>アップグレードの順序

トポロジを内側から外側にアップグレードします。 最初にすべてのプール、続いてエッジ サーバーをアップグレードして、最後に中央管理ストア (CMS) プールをアップグレードします。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 認証に関する考慮事項

Web サービスに Kerberos 認証を使用する場合は、一括アップグレードの完了後に、Kerberos アカウントを再割り当てしてパスワードをリセットする必要があります。 これを行う方法については、 [Kerberos 認証の設定](https://go.microsoft.com/fwlink/p/?LinkId=530342)を参照してください。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Lync Server 2013 および Lync Server 2010 との共存のサポート
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 は、Lync Server 2013 または Lync Server 2010 と同じトポロジで実行することができますが、3 つすべてを同じトポロジにすることはできません。
  
Lync Server 2010 と Lync Server 2013 が共存する場合は、トポロジ全体を Lync Server 2013 にアップグレードしてから、一括アップグレードを使用して Skype for Business Server 2015 にアップグレードすることをお勧めします。 詳細については、 [Lync Server 2013 に Lync Server 2010 の移行](https://go.microsoft.com/fwlink/p/?LinkId=526615)を参照してください。
  
使用するトポロジがおもに Lync Server 2010 である場合は、トポロジを Skype for Business Server 2015 にアップグレードする前に、Lync Server 2013 コンポーネントを Lync Server 2010 にロールバックします。その場合は、一括アップグレードを利用するメリットや、Lync Server 2010 と Skype for Business Server 2015 間でトポロジを共存させるメリットが得られません。
  
次の図は、Lync Server 2013 および Lync Server 2010 のビジネス サーバー 2015 の Skype の共存のサポートを示します。
  
![Lync Server 2013 または Lync Server 2010 との Skype for Business Server 2015 の共存のサポートを示している図](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>既存の存続可能ブランチ アプライアンスおよびサーバーを使用したアップグレード プロセス
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

ビジネス サーバー 2015 の Skype では、リカバリ性に優れたブランチ アプライアンス (SBA) のリカバリ性に優れたブランチ サーバー (SBS) のインプレース アップグレードをサポートしていません。
  
ただし、Skype for Business Server データセンターと Lync Server 2010 または Lync Server 2013 SBA/SBS の共存はサポートしています。 
  
Lync Server 2013 Front End (FE) プールとそれに関連付けられたブランチの一括アップグレードを計画する場合、Lync Server 2013 SBA/SBS の既存ユーザーは残すことができます。 アップグレード中、SBA/SBS ユーザーは復元モードになり、アップグレードが完了すると通常の機能に戻ります。 復元モードの間にユーザーのエクスペリエンスに関する詳細については、 [Lync Server 2013 の堅牢性に関する機能をブランチ サイト](https://technet.microsoft.com/library/gg398715.aspx)を参照してください。
  
Lync Server 2010 トポロジを Skype for Business Server 2015 に移行する場合は、Lync Server 2013 への移行と同様に、SBA/SBS をトポロジにもう一度追加する必要があります。 必要な手順については、 [Lync Server 2013 のフロント エンド プールへのリカバリ性に優れたブランチ アプライアンスの接続](https://technet.microsoft.com/library/jj688026.aspx)を参照してください。
  
Lync Server 2010 および Lync Server 2013 の共存トポロジに Lync Server 2013 および Lync Server 2010 との共存のサポート] セクションでの推奨事項には、1 つ目を配置します。
  
## <a name="see-also"></a>関連項目
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Environmental requirements for Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
