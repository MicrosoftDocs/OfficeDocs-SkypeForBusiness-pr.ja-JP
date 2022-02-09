---
title: 通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 通話品質ダッシュボード (CQD) に関してよく寄せられる質問 (FAQ) Microsoft Teams回答を参照してください。
ms.openlocfilehash: bd36fe70d46a190289749a96fbaadb8f6c176251
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457177"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

[1 人または複数の会議参加者の経験が低い場合、CQD が通話を "良好" とマークする理由](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[メジャーの呼び出しとユーザーカウントの値に最大 0.2% の差が表示される理由と、最も正確なボリュームを取得する方法 ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[CQD で EUII が表示できない理由](#why-cant-i-see-euii-in-cqd)

[使用タイプのレポートに CQD を使用しようとして、一部のデータが不完全であるのが分かっています。なぜですか?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[フィルター処理のみをSkype for Business、CQD に情報が表示Teams理由](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[追加のエントリが必要とわかっているのに、カスタム レポートで返される行数が最大 10,000 行になる理由](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[VPN 接続Wi-Fi Wi-Fi ではなく有線接続として表示される理由](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[Teams でポリシー ベースのレコーディングを有効にした後、ピアツーピア通話が電話会議としてマークされています。何が起こったのでしょうか。](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>1 人または複数の会議参加者の経験が低い場合、CQD が通話を "良好" とマークする理由

CQD がストリーム分類に使用する規則 [を確認してください](stream-classification-in-call-quality-dashboard.md)。
 
オーディオ ストリームの場合、5 つの分類子 (呼び出しの長さに基づいて平均に対して計算されます) はすべて "良好" パラメーター内に含まれます。 これは、ユーザーがオーディオのドロップアウト、静的、またはエラーの発生を経験しなかったことを意味する必要があります。 

ネットワークの問題かどうかを判断するには、セッションの平均値と最大値の差分を確認します。 最大値は、セッション中に検出され、報告される最大値です。
 
この状況をトラブルシューティングする方法の例を次に示します。 たとえば、通話中にネットワーク トレースを実行し、最初の 20 分間はパケットが失われることはありませんが、その後は 1.5 秒のパケットの間隔が生じ、通話の残りの部分に良好な時間が生じてしまいます。 平均は、Wireshark トレース RTP <でもパケット損失が 10% (0.1) 減少します。 最大パケット損失は何でしたか? 5 秒間の 1.5 秒は 30% (0.3) になります。 これは、5 秒間のサンプリング期間中に発生しましたか (または、サンプリング期間に分割される可能性があります)。
 
ネットワーク メトリックが平均値と最大値で良好に見える場合は、他のテレメトリ データを確認します。 
- [CPU Insufficient Event Ratio]をオンにし、検出された使用可能な CPU リソースが不十分で、低品質の原因になっているか確認します。 
- スピーカーに近すぎるマイクが理由でフィードバックを防ぐために、オーディオ デバイスは半二重モードでしたか? 
- デバイスの半分の両面 AEC イベントの比率を確認します。 マイクなどのデバイスから、ハブまたはドッキング ステーションに接続すると、USB オーディオのドロップアウトが原因でノイズや静的が発生しましたか?  
- デバイスの不具合とマイクの不具合イベントの比率を確認します。 デバイス自体が正しく機能していますか?  
- Capture デバイスと Render Device Not Functioning Event Ratios を確認します。


CQD テレメトリで使用できるディメンションとメジャーの詳細については、「通話品質ダッシュボードで使用できるディメンションと測定値 [」を参照してください](dimensions-and-measures-available-in-call-quality-dashboard.md)。

バックグラウンド ノイズの場合は、[ミュート イベントの比率] をオンにし、参加者がミュートされた時間の長さを確認します。
 
CQD で詳細なレポートを作成し、会議 ID でフィルター処理して、会議のすべてのユーザーとストリームを確認し、関心のあるフィールドを追加します。 問題を報告しているユーザーが、問題を発生しているユーザーではない可能性があります。 ユーザーはエクスペリエンスを報告しているだけです。
 
テレメトリは必ずしも問題を呼び出すとは限りませんが、決定を確認して通知する場所をよりよく理解するのに役立ちます。 ネットワーク、デバイス、ドライバーまたはファームウェアの更新プログラム、使用状況、またはユーザーですか。

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>メジャーの呼び出しとユーザーカウントの値に最大 0.2% の差が表示される理由と、最も正確なボリュームを取得する方法 

呼び出し数とユーザー数の測定を計算するために、データ セット内の呼び出しまたはユーザー識別子に対して個別の countif 操作が実行されます。 大規模なデータ セットでは、個別の countif 操作に固有の最大 0.2% のエラーがあります。 最も正確なボリュームの場合は、この個別のカウント演算に依存しならず、ストリーム数のメジャーに依存する必要があります。 データ 量を減らしてフィルター処理すると、エラーが減る可能性がありますが、個別の呼び出しとユーザー数でこのエラーの原因が排除されない場合があります。 メジャーが [影響を受ける方法については、「通話品質ダッシュボードで](dimensions-and-measures-available-in-call-quality-dashboard.md) 使用できるディメンションと測定値」を参照してください。

  
### <a name="why-cant-i-see-euii-in-cqd"></a>CQD で EUII が表示できない理由

これらの管理者ロールは CQD にアクセスできますが、EUII (エンド ユーザーが特定できる情報) を表示できません。

- Microsoft 365 レポート閲覧者
- Teams 通信サポート スペシャリスト

CQD にアクセスできるロール (EUII を含む) の詳細については、「CQD にアクセスするためにロールを割り当てる」 [を参照してください](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>使用タイプのレポートに CQD を使用しようとして、一部のデータが不完全であるのが分かっています。なぜですか?

CQD、Call Analytics、CallRecord Graph API、リアルタイム分析のような通話品質管理ツールは、診断テレメトリに基づいて行います。 通話品質管理ツールTeamsに表示される情報は、通話に参加しているクライアントから受信したテレメトリ データと同じに限り完全です。 ネットワークの停止、ファイアウォールまたはプロキシの構成ミスなど、完全なテレメトリが受信されない理由 [はいくつか考えます](/microsoft-365/enterprise/urls-and-ip-address-ranges.md)。 引き続き、クライアントがサービスにテレメトリを配信する信頼性Teams回復性の向上に取り組み続けています。

その念頭に置いて、通話品質管理ツールを使用した使用状況レポートの使用はサポートされていません。 このような種類のレポート シナリオに対応したり、意図したりすることを目的としていないので、多くの使用状況統計は、これらのツールでは使用できません。 Teams管理センターには一連の使用状況レポート[](teams-analytics-and-reports/teams-reporting-reference.md)が用意され、会議[](teams-analytics-and-reports/meeting-attendance-report.md)出席レポートは、クライアントから直接Teamsできます。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>フィルター処理のみをSkype for Business、CQD に情報がTeamsされる理由

CQD レポート (isTeams = 1) でのみ Teams をフィルター処理する場合は、最初のエンドポイントが呼び出されるすべての呼び出しをフィルター処理Teams。 2 *つ目の* エンドポイントSkype for Business、その情報が CQD レポートに表示されます。 お客様のシナリオに応じて、CQD には、Call [Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector.md) が構成されているSkype for Business Server 2019 の呼び出しが含まれる場合があります。 また、ボット呼びSkype (AA、CVI、VDI)、ライブ イベント、PSTN 通話も含まれます。

First *User Agent Category* や Skype for Business Second User *Agent Category* などのディメンションでフィルター処理することで、クエリから新しい情報を削除できます。 1 番目と *2 番目のディメンションを* 1 つのフィルターに結合するユーザー エージェント カテゴリ ペアを使用することもできます。

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>追加のエントリが必要とわかっているのに、カスタム レポートで返される行数が最大 10,000 行になる理由

CQD は集計されたデータ クエリ用に設計され、データエクスポート用には設計されません。 10,000 行の制限を超えないように、可能な限りレポートを再構築することをお勧めします。 まず、月、年、日付、地域、国などのより広いカーディナリティディメンションを使用して KPI を確認します。 そこから、より高いカーディナリティ ディメンションにドリルダウンできます。 ヘルプデスクレポートとLocation-Enhancedレポートはどちらも、このドリルダウン ワークフローの優れた例を提供します。

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>VPN 接続Wi-Fi Wi-Fi ではなく有線接続として表示される理由

これは想定された動作です。 VPN ベンダーは、有線接続と同様に扱われる仮想イーサネット アダプターを作成しました。 正しくラベル付けされていないので、オペレーティング システムは接続が正常なWi-Fi有線として報告します。

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>Teams でポリシー ベースのレコーディングを有効にした後、ピアツーピア通話が電話会議としてマークされています。何が起こったのでしょうか。

この動作は、ポリシー ベースの記録が有効になっている場合に、Microsoft Teams。 ポリシー ベースの記録では、Teamsにデプロイされた Microsoft Azure記録ボットを使用して、コンプライアンスの目的で会議の内容をキャプチャします。 通話品質管理では、"ピアツーピア" とは、ユーザー間のやり取りではなく、メディア トラフィックのフローの説明です。 レコーダー ボット自体が呼び出しの当事者なので、通話はピアツーピアではなく、マルチパーティ呼び出しです。 マルチパーティ通話は Microsoft Teams によって電話会議として分類されます。そのため、CQD や他の通話品質ツールでこれらの通話を表示すると、その通話が表示されます。

## <a name="related-articles"></a>関連記事

[Teams の通話品質の向上と監視](monitor-call-quality-qos.md)

[CQD とは](CQD-what-is-call-quality-dashboard.md)

[通話品質ダッシュボード (CQD) をセットアップする](turning-on-and-using-call-quality-dashboard.md)

[テナントと建物のデータをアップロードする](CQD-upload-tenant-building-data.md)

[CQD のデータとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD のストリーム分類](stream-classification-in-call-quality-dashboard.md)

[Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
