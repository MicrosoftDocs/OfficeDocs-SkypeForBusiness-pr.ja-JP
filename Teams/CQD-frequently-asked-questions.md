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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 通話品質ダッシュボード (CQD) に関してよく寄せられる質問 (FAQ) Microsoft Teams回答を参照してください。
ms.openlocfilehash: ad718df893b69b333dd63d224663238879fda8c7
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718008"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

[1 人または複数の会議参加者の経験が低い場合、CQD が通話を "良好" とマークする理由](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[メジャーの呼び出しとユーザーカウントの値に最大 0.2% の差が表示される理由と、最も正確なボリュームを取得する方法 ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[データからの CQD データがSkype for Business CQD データと異なるTeams。](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[CQD で EUII が表示できない理由](#why-cant-i-see-euii-in-cqd)

[フィルター処理のみをSkype for Business、CQD に情報が表示Teams。](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[追加のエントリが必要とわかっているのに、カスタム レポートで返される行数が最大 10,000 行になる理由](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[WiFi VPN 接続が WiFi ではなく有線として表示される理由](#why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>1 人または複数の会議参加者の経験が低い場合、CQD が通話を "良好" とマークする理由

CQD がストリーム分類に使用する規則 [を確認してください](stream-classification-in-call-quality-dashboard.md)。
 
オーディオ ストリームの場合、呼び出しの長さに基づいて平均に対して計算される 5 つの分類子は、すべて "良好" パラメーター内に含まれます。 これは、ユーザーがオーディオのドロップアウト、静的、またはエラーの発生を経験しなかったことを意味する必要があります。 

ネットワークの問題かどうかを判断するには、セッションの平均値と最大値の差分を確認します。 最大値は、セッション中に検出され、報告される最大値です。
 
この状況をトラブルシューティングする方法の例を次に示します。 たとえば、通話中にネットワーク トレースを実行し、最初の 20 分間はパケットが失われることはありませんが、その後は 1.5 秒のパケットの間隔が生じ、その後の通話の残りの部分に良好な差が生じてしまいます。 平均は、Wireshark トレース RTP <でも 10% (0.1) パケット損失が発生します。 最大パケット損失は何でしたか? 5 秒間の 1.5 秒は 30% (0.3) になります。 これは、5 秒間のサンプリング期間中に発生しましたか (または、サンプリング期間に分割される可能性があります)。
 
ネットワーク メトリックが平均値と最大値で良好に見える場合は、他のテレメトリ データを確認します。 
- [CPU Insufficient Event Ratio]をオンにし、検出された使用可能な CPU リソースが不十分で、低品質の原因になっているか確認します。 
- スピーカーに近いマイクによるフィードバックを防ぐために、オーディオ デバイスは半二重モードでしたか? 
- デバイスの半分の両面 AEC イベントの比率を確認します。 ハブまたはドッキング ステーションに接続すると、USB オーディオドロップアウトが原因で、デバイスのグリンクまたはマイクのグリンクによってノイズや静的が発生しましたか?  
- デバイスの不具合とマイクの不具合イベントの比率を確認します。 デバイス自体が正しく機能していますか?  
- Capture デバイスと Render Device Not Functioning Event Ratios を確認します。


CQD テレメトリで使用できるディメンションとメジャーの詳細については、「通話品質ダッシュボードで使用可能なディメンションと測定値 [」を参照してください](dimensions-and-measures-available-in-call-quality-dashboard.md)。

バックグラウンド ノイズの場合は、[ミュート イベントの比率] をオンにし、参加者がミュートされた時間の長さを確認します。
 
CQD で詳細なレポートを作成し、会議 ID でフィルター処理して、会議のすべてのユーザーとストリームを確認し、関心のあるフィールドを追加します。 問題を報告しているユーザーが、問題を発生しているユーザーではない可能性があります。 ユーザーはエクスペリエンスを報告しているだけです。
 
テレメトリは必ずしも問題を呼び出すとは限りませんが、決定を確認して通知する場所をよりよく理解するのに役立ちます。 ネットワーク、デバイス、ドライバーまたはファームウェアの更新プログラム、使用状況、またはユーザーですか。

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>メジャーの呼び出しとユーザーカウントの値に最大 0.2% の差が表示される理由と、最も正確なボリュームを取得する方法 
呼び出し数とユーザー数の測定を計算するために、データ セット内の呼び出しまたはユーザー識別子に対して個別の countif 操作が実行されます。 大規模なデータ セットでは、個別の countif 操作に固有の最大 0.2% のエラーがあります。 最も正確なボリュームの場合は、この個別の countif 操作に依存しならず、ストリーム数のメジャーに依存する必要があります。 データ 量を減らしてフィルター処理すると、エラーが減る可能性がありますが、個別の呼び出しとユーザー数でこのエラーの原因が排除されない場合があります。 メジャーが [影響を受け取る「通話品質](dimensions-and-measures-available-in-call-quality-dashboard.md) ダッシュボード」で使用できるディメンションと測定値に関するページを参照してください。


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>データからの CQD データがSkype for Business CQD データと異なるTeams。 


> [!IMPORTANT]
> 2020 年 7 月 1 日の現在、古い CQD (CQD.lync.com) では、最新の CQD (CQD.Teams.microsoft.com) のデータが使用されています。 古い CQD データは使用できなくなりました。また、建物データやレポート データをエクスポートできません。 引き続き CQD.lync.com (Skype for Business 管理センターから利用可能) を使用できますが、間もなく CQD.lync.com へのアクセスがオフになります。そのため、CQD に移行する必要があります。Teams.microsoft.com(まだ行っていない場合)。


Skype for Business レガシ ポータル (cqd.lync.com) の古い CQD と Teams 管理センター (cqd.teams.microsoft.com) の最新の CQD の間でデータを比較する場合、データが一致しないのがすぐに分かっています。 これは、最新の CQD が多くの追加の呼び出しシナリオを報告する理由です。 古い CQD のレポートを引き続き使用している場合は、この記事を使用して、これらのレポートを解釈するのに役立ちます。「通話品質ダッシュボード[for Skype for Business Server」](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)


  
### <a name="why-cant-i-see-euii-in-cqd"></a>CQD で EUII が表示できない理由

これらの管理者ロールは CQD にアクセスできますが、EUII (エンド ユーザーを特定できる情報) を表示できません。
- Microsoft 365レポート閲覧者
- Teams 通信サポート スペシャリスト

CQD にアクセスできるロール (EUII を含む) の詳細については、「CQD にアクセスするためにロールを割り当てる」 [を参照してください](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>フィルター処理のみをSkype for Business、CQD に情報が表示Teams。

CQD Teams レポート (isTeams = 1) でのみフィルター処理を行う場合は、最初のエンドポイントが含Teams。 2 *番目の* エンドポイントがSkype for Business、その情報が CQD レポートに表示されます。

CQDv2 と CQDv3 の合計カウントは常に異なります。CQDv3 には、CQDv2 にはない新しいシナリオが含まれています。 集計合計または集計された全数値をフィルターを使用して比較すると、これらの期待される違いが生じ得るのは、その理由です。  

顧客のシナリオに応じて、CQDv3 には SFB 2019 オンプレミス呼び出し (SFB 2019 がデータ コネクタで使用されている場合)、Skype ボット呼び出し (AA、CVI、VDI)、ライブ イベント、PSTN 通話が含まれます。 顧客が利用できるが、データが CQD V2 内にはないシナリオ/機能。

たとえば、顧客と 200,000 のオーディオ ストリームが表示され、CQD V2 サマリー レポートで 5000 エラーが発生すると想定されます。CQD V3 では、300,000 のオーディオ ストリームと 5500 の障害 (2019 年のオンプレム通話、CVI 呼び出し、PSTN 通話など) が発生します。

予期しない違いがある場合は、データ全体のさまざまな内訳を確認する必要があります。  意図と比較します。  ユーザー エージェント カテゴリ ペアによるデータのスライスは、最初に推奨される項目の 1 つです。  *First Product と* *Second Product* も優れたスライサーです。  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>追加のエントリが必要とわかっているのに、カスタム レポートで返される行数が最大 10,000 行になる理由

CQD は集計されたデータ クエリ用に設計され、データエクスポート用には設計されません。 可能であれば、10,000 行の制限を超えないように、レポートを再構築することをお勧めします。 まず、月、年、日付、地域、国など、より広範なカーディナリティディメンションを使用して KPI を確認します。そこから、より高いカーディナリティ ディメンションにドリルダウンできます。 ヘルプデスクレポートとLocation-Enhancedレポートはどちらも、このドリルダウン ワークフローの優れた例を提供します。

### <a name="why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi"></a>WiFi VPN 接続が WiFi ではなく有線として表示される理由

これは予期されることです。 VPN ベンダーは、有線接続として扱われる仮想イーサネット アダプターを作成しました。 正しくラベル付けされていないので、オペレーティング システムは WiFi 接続を知らないので、有線として報告します。

## <a name="related-topics"></a>関連項目

[Teams の通話品質の向上と監視](monitor-call-quality-qos.md)

[CQD とは](CQD-what-is-call-quality-dashboard.md)

[通話品質ダッシュボード (CQD) を設定する](turning-on-and-using-call-quality-dashboard.md)

[アップロードとデータの構築](CQD-upload-tenant-building-data.md)

[CQD データとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で使用可能なディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD のストリーム分類](stream-classification-in-call-quality-dashboard.md)

[CQD Power BI分析するには、次のコマンドを使用します。](CQD-Power-BI-query-templates.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
