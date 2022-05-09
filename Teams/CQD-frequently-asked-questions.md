---
title: 通話品質ダッシュボード (CQD) よく寄せられる質問 (FAQ)
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
description: よく寄せられる質問 (FAQ) とMicrosoft Teams通話品質ダッシュボード (CQD) に関する回答を参照してください。
ms.openlocfilehash: 3d795393f99765ab445a5495b626ebd9b8722131
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592932"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>通話品質ダッシュボード (CQD) よく寄せられる質問 (FAQ)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

[1 人以上の会議参加者の経験が低い場合、CQD によって通話が "良い" とマークされるのはなぜですか?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[メジャーの呼び出しとユーザー数の値に最大 0.2% の違いがあり、最も正確なボリュームを取得する方法が表示されるのはなぜですか? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[CQD で EUII が表示されないのはなぜですか?](#why-cant-i-see-euii-in-cqd)

[使用状況の種類のレポートに CQD を使用しようとしていますが、データの一部が不完全であることがわかります。なぜですか?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[Teamsのみをフィルター処理した場合に CQD にSkype for Business情報が表示されるのはなぜですか?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[カスタム レポートで返される行数が最大で 10,000 行しかないのに、エントリが増える必要があることがわかっているのはなぜですか?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Wi-Fi VPN 接続が Wi-Fi の代わりにワイヤード (有線) と表示されるのはなぜですか?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[Teamsでポリシーベースのレコーディングをオンにし、ピアツーピア通話が電話会議としてマークされるようになりました。何が起こったのか。](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>1 人以上の会議参加者の経験が低い場合、CQD によって通話が "良い" とマークされるのはなぜですか?

[CQD がストリーム分類](stream-classification-in-call-quality-dashboard.md)に使用するルールを確認してください。
 
オーディオ ストリームの場合、5 つの分類子 (呼び出しの長さに基づいて平均で計算されます) はすべて"良好" パラメーター内に含まれる可能性があります。 これは、ユーザーがオーディオのドロップアウト、静的、または不具合に貢献した何かを経験しなかったことを意味するわけではありません。 

ネットワークの問題かどうかを確認するには、セッションの平均値と最大値の間の差分を調べます。 最大値は、セッション中に検出および報告される最大値です。
 
この状況をトラブルシューティングする方法の例を次に示します。 たとえば、呼び出し中にネットワーク トレースを取得し、最初の 20 分間はパケットが失われませんが、パケットの間隔は 1.5 秒で、残りの呼び出しには適しているとします。 平均は、Wireshark トレース RTP 分析でも 10% (0.1) パケット損失を<します。 最大パケット損失は何でしたか? 5 秒間の 1.5 秒は 30% (0.3) になります。 これは 5 秒のサンプリング期間内に発生しましたか (サンプリング期間に分割される可能性もあります)。
 
ネットワーク メトリックが平均値と最大値に適している場合は、他のテレメトリ データを参照してください。 
- CPU 不十分なイベント比を確認して、検出された使用可能な CPU リソースが不足し、品質が低下したかどうかを確認します。 
- マイクがスピーカーに近すぎるため、フィードバックを防ぐため、オーディオ デバイスは半二重モードでしたか? 
- デバイスの半二重 AEC イベント比を確認します。 ハブやドッキング ステーションに接続すると USB オーディオのドロップアウトが原因で、マイクなどのデバイスから不具合が発生し、ノイズや静的が発生しましたか?  
- デバイスの不具合とマイクの不具合イベントの比率を確認します。 デバイス自体は正常に機能していましたか?  
- キャプチャとレンダリング デバイスが機能しないイベント比を確認します。


CQD テレメトリで使用できるディメンションとメジャーの詳細については、 [通話品質ダッシュボードで使用できるディメンションと測定値](dimensions-and-measures-available-in-call-quality-dashboard.md)を参照してください。

バックグラウンド ノイズの場合は、ミュート イベントの比率を確認して、参加者がミュートされた時間の長さを確認します。
 
CQD で詳細なレポートを作成し、会議 ID でフィルター処理して、会議内のすべてのユーザーとストリームを表示し、関心のあるフィールドを追加します。 問題を報告するユーザーは、問題が発生していたユーザーではない可能性があります。 彼らは、エクスペリエンスを報告しているだけです。
 
テレメトリは必ずしも問題を呼び出すわけではありませんが、決定事項を確認して通知する場所をよりよく理解するのに役立ちます。 ネットワーク、デバイス、ドライバー、ファームウェアの更新、使用状況、またはユーザーですか?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>メジャーの呼び出しとユーザー数の値に最大 0.2% の違いがあり、最も正確なボリュームを取得する方法が表示されるのはなぜですか? 

呼び出し数とユーザー数のメジャーを計算するために、データ セット内の呼び出しまたはユーザー識別子に対して個別の countif 操作が実行されます。 大規模なデータ セットでは、個別の countif 操作に固有の最大 0.2% のエラーが発生します。 最も正確なボリュームの場合は、この個別の countif 操作に依存しないため、ストリーム数メジャーに依存する必要があります。 データ 量を減らすフィルター処理ではエラーが減少する可能性がありますが、個別の呼び出しとユーザー数でこのエラーの原因を排除できない場合があります。 メジャーが影響を受ける [通話品質ダッシュボードで使用できるディメンションと測定値](dimensions-and-measures-available-in-call-quality-dashboard.md) を参照してください。

  
### <a name="why-cant-i-see-euii-in-cqd"></a>CQD で EUII が表示されないのはなぜですか?

これらの管理者ロールは CQD にアクセスできますが、EUII (エンド ユーザーが識別できる情報) を表示することはできません。

- Microsoft 365 レポート 閲覧者
- Teams 通信サポート スペシャリスト

CQD にアクセスできるロール (EUII を含む) の詳細については、「 [CQD にアクセスするためのロールの割り当て](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)」を参照してください。

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>使用状況の種類のレポートに CQD を使用しようとしていますが、データの一部が不完全であることがわかります。なぜですか?

CQD、Call Analytics、CallRecord Graph API、リアルタイム分析などの通話品質管理ツールは、診断テレメトリに基づいています。 通話品質管理ツールTeams表示する情報は、通話に参加しているクライアントから受け取るテレメトリ データと同じくらい完全です。 ネットワークの停止、 [ファイアウォールやプロキシの構成の誤](/microsoft-365/enterprise/urls-and-ip-address-ranges)りなど、完全なテレメトリを受信できない理由はいくつかあります。 Teams クライアントがサービスにテレメトリを提供する信頼性と回復性の向上に引き続き取り組みます。

この点を念頭に置いて、使用状況レポートに通話品質管理ツールを使用することはサポートされていません。 これらは、このような種類のレポート シナリオに対応したり意図したりするように設計されておらず、多くの使用状況統計は、これらのツール内では使用できません。また、使用できません。 Teams管理センターには一連の[使用状況レポート](teams-analytics-and-reports/teams-reporting-reference.md)が用意されており、[会議出席レポート](teams-analytics-and-reports/meeting-attendance-report.md)はTeams クライアントから直接入手できます。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Teamsのみをフィルター処理した場合に CQD にSkype for Business情報が表示されるのはなぜですか?

CQD レポートでのみTeamsをフィルター処理する場合 (isTeams = 1) は、*最初のエンドポイント* がTeamsされているすべての呼び出しをフィルター処理します。 *2 番目のエンドポイント* がSkype for Businessされている場合、その情報は CQD レポートに表示されます。 顧客のシナリオによっては、[データ コネクタの呼び出](/skypeforbusiness/hybrid/plan-call-data-connector.md)しが構成されている場合、CQD には 2019 Skype for Business Server呼び出しが含まれる場合があります。 また、Skype Bot 通話 (AA、CVI、VDI)、ライブ イベント、PSTN 通話も含まれる場合があります。

最初のユーザー エージェント カテゴリや *2 番目* の *ユーザー エージェント カテゴリ* などのディメンションをフィルター処理することで、クエリからSkype for Business情報を削除できます。 また、1 つのフィルターに 1 つの第 1 ディメンションと第 2 ディメンションを組み合わせた *ユーザー エージェント カテゴリ ペア* を使用することもできます。

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>カスタム レポートで返される行数が最大で 10,000 行しかないのに、エントリが増える必要があることがわかっているのはなぜですか?

CQD は、集計されたデータ クエリ用に設計されており、データエクスポート用には設計されていません。 可能であれば、レポートを再構築して、10,000 行の制限を超えないようにすることをお勧めします。 まず、月、年、日付、地域、国など、より広範でカーディナリティの低いディメンションを使用して KPI を確認します。 そこから、カーディナリティの高いディメンションをドリルダウンできます。 ヘルプデスクレポートとLocation-Enhancedレポートはどちらも、このドリルダウン ワークフローの優れた例を提供します。

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>Wi-Fi VPN 接続が Wi-Fi の代わりにワイヤード (有線) と表示されるのはなぜですか?

これは想定された動作です。 VPN ベンダーは、有線接続のように扱われる仮想イーサネット アダプターを作成しました。 適切なラベルが付いていないため、オペレーティング システムは、それがWi-Fi接続であることを認識せず、ワイヤード (有線) として報告します。

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>Teamsでポリシーベースのレコーディングをオンにし、ピアツーピア通話が電話会議としてマークされるようになりました。何が起こったのか。

これは、Microsoft Teamsでポリシー ベースの記録が有効になっている場合に想定される動作です。 ポリシー ベースの記録では、Microsoft Azureに展開されたTeamsレコーダー ボットを使用して、コンプライアンスを目的として会議の内容をキャプチャします。 通話品質管理では、"ピアツーピア" は、ユーザー間の対話ではなく、メディア トラフィックのフローの説明です。 レコーダー ボット自体が通話の当事者であるため、通話はピアツーピアではなく、複数パーティの呼び出しです。 マルチパーティ通話はMicrosoft Teams別に電話会議として分類されるため、CQD やその他の通話品質ツールでこれらの通話を表示すると、そのように表示されます。

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
