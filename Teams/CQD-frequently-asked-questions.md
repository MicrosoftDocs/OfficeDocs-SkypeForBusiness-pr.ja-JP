---
title: 通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: よく寄せられる質問 (FAQ) と、Microsoft Teams の通話品質ダッシュボード (CQD) に関する回答を参照してください。
ms.openlocfilehash: f33d66d9c8abb465c6680bacbbd2ff200cf930c6
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086173"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

[1人以上の会議の出席者が不適切なエクスペリエンスをした場合、CQD は "Good" として通話をマークするのはなぜですか?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[メジャーの通話回数とユーザー数の値に0.2% の差が表示されるのはなぜですか。また、正確なボリュームを取得するにはどうすればよいですか?](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[CQD v2 のレポートデータが CQD v3 のレポートデータと異なるのはなぜですか?](#why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data)

[Skype for Business からの CQD データが Teams の CQD データと異なっているのはなぜですか?](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[CQD で EUII が表示されるのはなぜですか?](#why-cant-i-see-euii-in-cqd)

[チームのみを対象としてフィルター処理したときに、CQD に Skype for Business の情報が表示されるのはなぜですか?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>1人以上の会議の出席者が不適切なエクスペリエンスをした場合、CQD は "Good" として通話をマークするのはなぜですか?

CQD で[ストリームの分類](stream-classification-in-call-quality-dashboard.md)に使用するルールを確認します。
 
オーディオストリームについては、呼び出しの長さに基づいて平均値に基づいて計算される5つの分類子のいずれかが "good" パラメーター内に存在する可能性があります。 これは、ユーザーがオーディオのドロップアウト、静的、または故障に寄与するものを経験していなかったことを意味します。 

ネットワークの問題であったかどうかを判断するには、セッションの平均値と最大値の間のデルタを確認します。 [最大値] は、セッション中に最大検出および報告された値です。
 
このような状況のトラブルシューティングを行う方法の例を次に示します。 通話中にネットワークトレースを取得したときに、最初の20分間のパケットが失われても、1.5 秒のパケットが残っていて、通話の残りの部分に適しているとします。 この平均値は、Wireshark trace RTP の分析であっても、10% (0.1) のパケット損失と <なります。 パケット損失の最大値は何ですか? 1.5 秒の間の秒数は、30% (0.3) です。 5番目のサンプリング期間内に発生しましたか (おそらく、サンプリング期間に分割されている可能性があります)?
 
ネットワークメトリックが [平均] と [最大値] に適切に表示される場合は、他のテレメトリデータを参照します。 
- CPU 不足イベント比率を確認して、検出された CPU リソースが不足していて、品質が低品質であるかどうかを確認します。 
- スピーカーに近いマイクによるフィードバックを防ぐため、半二重モードのオーディオデバイスになりましたか? 
- デバイスの半二重 AEC イベント比率を確認します。 ハブまたはドッキングステーションに接続したときに、USB オーディオのドロップアウトによって、デバイスグリッチノイズまたはマイクグリッチノイズ音が聞こえます。  
- デバイスのエラーとマイクのイベント比率を確認します。 デバイス自体が正常に機能していますか?  
- キャプチャとレンダリングデバイスが機能していないことを確認します。


CQD テレメトリで利用できるディメンションとメジャーの詳細については、「[通話品質ダッシュボードで利用可能なディメンションと測定値](dimensions-and-measures-available-in-call-quality-dashboard.md)」を参照してください。

バックグラウンドノイズの場合は、[ミュートイベント比率] チェックボックスをオンにして、参加者がミュートにした時間の長さを確認します。
 
CQD で詳細なレポートを作成し、会議 ID にフィルターを適用して、会議のすべてのユーザーとストリームを確認し、目的のフィールドを追加します。 問題を報告しているユーザーが、問題が発生しているユーザーでない可能性があります。 経験を報告しているだけです。
 
テレメトリによって問題が発生するとは限りませんが、お客様の意思決定を確認して通知する方法を理解するのに役立ちます。 ネットワーク、デバイス、ドライバーまたはファームウェアの更新、使用、またはユーザーのどちらを使用していますか?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>メジャーの通話回数とユーザー数の値に0.2% の差が表示されるのはなぜですか。また、正確なボリュームを取得するにはどうすればよいですか? 
通話カウントとユーザーカウントのメジャーを計算するために、個別の countif 操作が、データセット内の呼び出しまたはユーザー id に対して実行されます。 大きなデータセットでは、個別の countif 操作に固有の最大0.2% のエラーがあります。 最も正確なボリュームの場合は、この個別の countif 操作に依存しないため、ストリームカウントのメジャーに依存している必要があります。 データの量を減らすためにフィルター処理を行うと、エラーが発生する可能性がありますが、個別の通話とユーザーカウントでこのエラーの原因が解消されない場合があります。 メジャーに影響を与える[通話品質ダッシュボードで利用可能な寸法と測定値](dimensions-and-measures-available-in-call-quality-dashboard.md)を参照してください。

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>CQD v2 のレポートデータが CQD v3 のレポートデータと異なるのはなぜですか? 

CQD v2 と v3 のデータの違いが表示される場合は、データの比較または検証が、集計レベルではなく、"りんごからりんご" と "幅" レベルで行われていることを確認してください。 たとえば、"建物 30" の WiFi Teams のデスクトップクライアントデータの両方のレポートをフィルター処理する場合、低品質の割合は、v2 と v3 で同じである必要があります。

CQDv2 の呼び出しセットアップエラーは、"オーディオ" のモダリティでのみ考慮され、CQDv3 では、すべてのモダリティ (オーディオ、ビデオ、Appsharing) に対してこの分類が発生し、各モダリティストリームで表されます。 

Teams の場合、CQDv2 はすべてのモダリティ CQDv3 に同じユーザーフィードバックを適用し、Teams のモダリティにフィードバックベースを適用します。

CQD V3 の内容 
1. Skype for Business Server の2019通話 
2. Skype ボット通話 (自動応答、通話キュー、会議アナウンスメントサービスなど) 
3. 仮想デスクトップインターフェイス、
4. 会議ビデオの相互運用機能、
3. ライブイベントの発行元と発表者の通話 
4. PSTN 通話。 

これらの Power BI テンプレートを使用して CQD データを分析して報告する方法については、「 [POWER bi FOR CQD レポートを使用](cqd-power-bi-query-templates.md)する」を参照してください。


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Skype for Business からの CQD データが Teams の CQD データと異なっているのはなぜですか? 


> [!IMPORTANT]
> 2020年7月1日以降、古い CQD は最新の CQD のデータにアクセスします。 古い CQD データは利用できなくなり、文書の作成やレポートのデータをエクスポートすることはできません。


以前の CQD と Skype for Business の従来のポータル (cqd.lync.com) と最新の CQD の間でデータを比較しようとしている場合は、データが一致していないことがすぐにわかります。 これは、最新の CQD で多くの追加の通話シナリオが報告されるためです。 以前の CQD のレポートを引き続き使用している場合は、この記事を参照してください。これらのレポートは、 [Skype For Business Server の通話品質ダッシュボード](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)を使って解釈することができます。



次に、CQD v2 と CQD v3 のデータを比較するために特定のフィルターを適用する例を示します。

1. 使用可能な QoE レコード = True

2. [追加] は、サーバーペアフィルターの値: Client: client and Client: Server。 ほとんどのテナントでは、サーバー呼び出しを除外します。

3. ユーザーエージェントカテゴリのフィルターを追加し、自動アテンダント、通話キュー、ボット、Room system、MediationServer、会議アナウンスメントサービス、VDI などのフィルターを追加します。

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard1.png" alt-text="CQD v3 での特定のフィルターの適用のスクリーンショット":::

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard2.png" alt-text="CQD v2 での特定のフィルターの適用のスクリーンショット":::

#### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>CQD v2 と CQD v3 とのその他の予想される違い

以前の CQD と最新のバージョンの違いの詳細については、 [「Advanced Call Quality ダッシュボードの](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586)ブログを2019年11月5日から紹介する」を参照してください。


> [!IMPORTANT]
> 2020年7月1日以降、古い CQD は最新の CQD のデータにアクセスします。 古い CQD データは利用できなくなり、文書の作成やレポートのデータをエクスポートすることはできません。

以前のバージョンと新しい CQD のレポートでは、集計または概要レベルでより多くのデータの相違が表示される可能性があります。 データをより細かいレベルで比較すると、"リンゴからりんご" の比較が表示されます。 たとえば、個々の建物のデータを見ている場合、低品質のパーセンテージは、以前の CQD レポートと新しいレポートの両方で同じである必要があります。

- 会社の有線接続、Windows デスクトップ、または1つの地域や建物など、集中するシナリオを選択します。
- Teams の [MR]、[TR]、または [MP] の IP 範囲を確認します。 Teams の範囲は、Skype for Business Online よりも新しいものであり、ファイアウォールに関する接続の問題が発生する可能性があります。
- サマリーまたはトップレベルの数値を比較しないでください。 これらの比較を行うことで、企業の有線接続での Skype for Business Online 通話の大きな通話音量と、LTE またはプライベートネットワーク上での少人数のチーム通話との比較を行うことができます。
- 位置のバイアスと母集団の相違点に注意してください。多すぎては、次のような違いがあります。
  - NOAM: APAC
  - NY: Goa
  - 有線 : WiFi
  - 企業ネットワーク: ホームネットワーク
  
### <a name="why-cant-i-see-euii-in-cqd"></a>CQD で EUII が表示されるのはなぜですか?

次の管理者ロールは、CQD にアクセスできますが、EUII (エンドユーザーを特定できる情報) を表示することはできません。
- Microsoft 365 レポートリーダー
- Teams 通信サポート スペシャリスト

CQD にアクセスできる役割の詳細については、「 [CQD にアクセスするための役割の割り当て](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)」を参照してください。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>チームのみを対象としてフィルター処理したときに、CQD に Skype for Business の情報が表示されるのはなぜですか?

CQD レポート (isTeams = 1) でのみチームをフィルター処理している場合、*第1のエンドポイント*が Teams であるすべての通話をフィルター処理します。 *第2のエンドポイント*が Skype for business の場合、その情報が CQD レポートに表示されます。

CQDv2 と CQDv3 は、CQDv2 にはない新しいシナリオが用意されているため、常に合計数が異なる場合があります。 このため、サマリーの合計を比較したり、フィルターを使わずにすべての数値を集計したりすると、このような違いがあります。  

お客様のシナリオに応じて、CQDv3 には SFB 2019 オンプレミスの通話 (データコネクタと共に SFB 2019 を使用している場合)、Skype ボット通話 (AA、CVI、VDI)、ライブイベント、PSTN 通話が含まれます。 顧客に提供されているが、そのデータは CQD V2 に含まれていないシナリオ/機能。

たとえば、お客様には、20万オーディオストリームが表示され、CQD V2 サマリーレポートで5000エラーが発生することが予想されます。CQD V3 の5500のエラー (2019 オンプレミス通話、CVI 通話、PSTN 通話など) と30万オーディオストリーム。

予期しない違いがある場合は、データ全体のさまざまな内訳を確認する必要があります。  目的に合わせて比較します。  ユーザーエージェントカテゴリペア別のデータのスライスは、最初に推奨されるものの1つです。  *第1の製品*と*第2の製品*は、スライサーとしても優れています。  


## <a name="related-topics"></a>関連項目

[Teams の通話品質を向上させて監視する](monitor-call-quality-qos.md)

[CQD とは何ですか?](CQD-what-is-call-quality-dashboard.md)

[通話品質ダッシュボード (CQD) を設定する](turning-on-and-using-call-quality-dashboard.md)

[テナントのアップロードとデータの構築](CQD-upload-tenant-building-data.md)

[CQD データとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で使用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD でのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)

[チームのトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)