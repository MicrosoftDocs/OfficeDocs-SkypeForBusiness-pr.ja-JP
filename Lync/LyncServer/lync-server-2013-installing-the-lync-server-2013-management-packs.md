---
title: Lync Server 2013 管理パックのインストール
TOCTitle: Lync Server 2013 管理パックのインストール
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48273356
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 管理パックのインストール

 

_**トピックの最終更新日:** 2016-12-08_

System Center Operations Manager は、単独では Windows オペレーティング システムのごく一部しか監視できません。ただし、System Center Operations Manager の機能は管理パックをインストールすることによって拡張することができます。管理パックとは System Center Operations Manager が監視できる項目を決定するソフトウェアで、これらの項目の監視方法、通知をトリガーおよび報告する方法が含まれています。Microsoft Lync Server 2013 には、次の機能を提供する 2 つの System Center Operations Manager 管理パックが含まれています。

  - コンポーネントおよびユーザー管理パック (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) では、イベント ログに記録されている、パフォーマンス カウンターに登録されている、または詳細な通話の記録 (CDR) や QoE (Quality of Experience) データベースに記録されている、Lync Server の問題を追跡します。重大な問題では、電子メール、インスタント メッセージ、またはショート メッセージ サービス (SMS) メッセージングを使用して管理者にすぐに通知するように System Center Operations Manager を構成することができます。SMS とは、テキスト メッセージをモバイル デバイス間で送信するために使用されるテクノロジです。
    
    > [!NOTE]
    > Operations Manager の通知の構成の詳細については、TechNet ライブラリの「通知の構成」(<a href="http://go.microsoft.com/fwlink/?linkid=268785%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268785&amp;clcid=0x411</a>) を参照してください。


  - アクティブ監視パック (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) では、システムへのログオン、インスタント メッセージの交換、公衆交換電話網 (PSTN) 上の電話への発信などの主要な Lync Server コンポーネントを事前にテストします。これらのテストは、Lync Server 代理トランザクション コマンドレットを使用して実行します。たとえば、**Test-CsIM** コマンドレットは、1 組のテスト ユーザー間でインスタント メッセージングの会話をシミュレートするために使用されます。シミュレートされたメッセージングの会話が失敗した場合、通知が生成されます。

Lync Server 2013 に含まれる 2 つの管理パックには、Microsoft Lync Server 2010 で使用される管理パックにおける多数の強化機能が含まれています。たとえば、Lync Server 2013 コンポーネント管理パックは Lync Server 自体の監視に制限されていません。コンポーネント管理パックでは、Lync Server のイベント ログおよびパフォーマンス カウンターの監視だけでなく、次のような重要な項目のパフォーマンスおよび問題通知も追跡することができます。

  - **インターネット インフォメーション サービス (IIS)**   インターネット インフォメーション サービスがオフラインになると通知が発行されます。Lync Server Web サービスは IIS に依存するため、これは重要です。

  - **プロセス使用率**   システム リソース (使用可能なメモリなど) が不足し始めると通知が発行されます。これらの通知は、Lync Server が高いシステム使用率の原因ではない場合でも発行されます。

  - **コンピューターの障害イベント**   サーバーの存続可能性が脅かされるハードウェアまたはソフトウェアの問題が発生した場合に通知が発行されます。たとえば、サーバーにハード ディスク障害の危険があると考えられる場合は Lync Server 管理者に通知されます。

新しい管理パックは、拡張されたレポート機能も備えています。Lync Server 2013 には次の新しいレポートがあります。

  - **エンドツーエンド シナリオの可用性レポート**   このレポートは、登録やプレゼンスなどの Lync Server の主要なサービスに関する可用性または稼働時間について詳述します。

  - **処理能力レポート**   このレポートは、パフォーマンス カウンターの情報を使用して、メモリの状態やプロセッサの使用率などのシステム コンポーネントの傾向を示します。

  - **コンポーネント レポート**   このレポートは、Lync Server コンポーネントによってグループ化された上位の通知生成元を一覧に表示します。

これらの事前に設計されたレポートに加え、Lync Server 2013 の管理パックは通話の信頼性 (通話詳細記録によって測定される指標) と QoE 状態 (QoE によって測定される指標) の両方で自動的に通知をレポートします。通話詳細記録を有効にしている場合、System Center Operations Manager コンソールから次の手順を実行することによって通話の信頼性の通知を確認できます。

  - \[**監視**\]、\[**Microsoft Lync Server 2013 Health**\]、\[**Call Reliability and Media Quality**\] の順に展開し、\[**Call Reliability**\] をクリックします。

QoE 通知を表示するには、System Center Operations Manager コンソールから次の手順を実行します。

  - \[**監視**\]、\[**Microsoft Lync Server 2013 Health**\]、\[**Call Reliability and Media Quality**\]、\[**Media Quality**\] の順に展開します。

Lync Server 2013 の管理パックでは、Microsoft Lync Server 2010 で使用されている中央検出メカニズムではなく、マシンレベルの検出を使用するようになりました。これは、各 System Center エージェントは基本的に自身を検出して中央管理サーバーに自身の存在を報告することを意味します。マシンレベルの検出を使用すると System Center インフラストラクチャの管理が容易になり、異なるバージョンの Lync Server 管理パック (たとえば Lync Server 2010 の管理パックとLync Server 2013 の管理パック) も共存できるようになります。

