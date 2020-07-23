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
ms.openlocfilehash: 43dd0f85c21914320ff48c2e0aab82614670ff90
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372126"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

[1人以上の会議の出席者が不適切なエクスペリエンスをした場合、CQD は "Good" として通話をマークするのはなぜですか?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[メジャーの通話回数とユーザー数の値に0.2% の差が表示されるのはなぜですか。また、正確なボリュームを取得するにはどうすればよいですか?](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

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


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Skype for Business からの CQD データが Teams の CQD データと異なっているのはなぜですか? 


> [!IMPORTANT]
> 2020年7月1日の時点では、古い CQD (CQD.lync.com) は最新の CQD (CQD のデータを使用しています。Teams.microsoft.com)。 古い CQD データは利用できなくなり、文書の作成やレポートのデータをエクスポートすることはできません。 引き続き CQD.lync.com (Skype for Business 管理センターから利用可能) は使用できますが、CQD.lync.com へのアクセスはすぐにオフにするため、CQD に移動する必要があります。まだインストールしていない場合は、Teams.microsoft.com します。


以前の CQD と Skype for Business の従来のポータル (cqd.lync.com) と最新の CQD の間でデータを比較しようとしている場合は、データが一致していないことがすぐにわかります。 これは、最新の CQD で多くの追加の通話シナリオが報告されるためです。 以前の CQD のレポートを引き続き使用している場合は、この記事を参照してください。これらのレポートは、 [Skype For Business Server の通話品質ダッシュボード](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)を使って解釈することができます。


  
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

[Teams のトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)