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
description: Microsoft Teams 通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ) と回答をお読みください。
ms.openlocfilehash: 3b527b32e194b531be5003c5f8b180a00976cf8e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111533"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>通話品質ダッシュボード (CQD) についてよく寄せられる質問 (FAQ)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

[1 人または複数の会議参加者のエクスペリエンスが低下した場合、CQD は通話を "良い" とマークする理由を示します。](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[メジャーの呼び出しとユーザー 数の値に最大 0.2% の差が表示される理由と、最も正確なボリュームを取得する方法 ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Skype for Business の CQD データが Teams の CQD データと異なる理由 ](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[CQD に EUII が表示できない理由](#why-cant-i-see-euii-in-cqd)

[Teams のみをフィルター処理した場合に、CQD に Skype for Business の情報が表示される理由](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[追加のエントリが必要とわかっているのに、カスタム レポートで返される行数が最大 10,000 行である理由](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>1 人または複数の会議参加者のエクスペリエンスが低下した場合、CQD は通話を "良い" とマークする理由を示します。

ストリームの分類に CQD が使用するルール [を確認します](stream-classification-in-call-quality-dashboard.md)。
 
オーディオ ストリームの場合、呼び出しの長さに基づいて平均に対して計算される 5 つの分類子はすべて "良好" パラメーター内に含まれます。 これは、ユーザーがオーディオのドロップ アウト、静的、またはエラーの発生を経験しなかったという意味では意味されません。 

ネットワークの問題かどうかを判断するには、セッションの平均値と最大値の差分を確認します。 最大値は、セッション中に検出および報告される最大値です。
 
この状況のトラブルシューティングを行う方法の例を次に示します。 たとえば、通話中にネットワーク トレースを実行し、最初の 20 分間はパケットが失われなくなっても、1.5 秒のパケットの間隔が生じ、通話の残りの部分に有効だとします。 平均は、Wireshark トレース RTP 分析<10% (0.1) パケット損失に対応する予定です。 最大パケット損失は何でしたか? 5 秒の 1.5 秒は 30% (0.3) になります。 これは 5 秒のサンプリング期間内に発生しましたか (または、サンプリング期間を超える場合に分割される可能性があります)。
 
ネットワークメトリックが平均と最大値で良好に表示される場合は、他のテレメトリ データを確認します。 
- [CPU Insufficient Event Ratio] をチェックして、使用可能な検出された CPU リソースが不足し、低品質の原因になっているか確認します。 
- スピーカーに近いマイクによるフィードバックを防ぐために、オーディオ デバイスは半両面モードでしたか? 
- Device Half Duplex AEC Event Ratio を確認します。 ハブまたはドッキング ステーションに接続すると、USB オーディオ のドロップアウトが原因でノイズまたは静的なノイズが発生したデバイスまたはマイク gling でした。  
- デバイスの不具合とマイクの不具合のイベント比率を確認します。 デバイス自体は正常に機能しましたか?  
- キャプチャ デバイスとレンダー デバイスが機能しないイベント 比を確認します。


CQD テレメトリで利用できるディメンションとメジャーの詳細については、「通話品質ダッシュボードで利用できるディメンションと測定値」 [を参照してください](dimensions-and-measures-available-in-call-quality-dashboard.md)。

背景の雑音の場合は、ミュート イベントの比率を確認して、参加者がミュートにされた時間の長さを確認します。
 
CQD で詳細レポートを作成し、会議 ID をフィルター処理して、会議のすべてのユーザーとストリームを確認し、関心のあるフィールドを追加します。 問題を報告しているユーザーが、問題を発生しているユーザーではない可能性があります。 これらのユーザーは、そのエクスペリエンスを報告しています。
 
テレメトリは必ずしも問題を呼び出すとは限りませんが、どこで決定を見て通知する必要があるのかをよりよく理解するのに役立ちます。 ネットワーク、デバイス、ドライバー、またはファームウェアの更新プログラム、使用状況、またはユーザーですか?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>メジャーの呼び出しとユーザー 数の値に最大 0.2% の差が表示される理由と、最も正確なボリュームを取得する方法 
呼び出し数とユーザー数のメジャーを計算するには、データ セット内の呼び出しまたはユーザー識別子に対して個別の countif 操作が実行されます。 大きなデータ セットの場合、個別の countif 操作に固有のエラーは最大 0.2% です。 最も正確なボリュームの場合は、この個別の countif 操作に依存しないので、ストリーム カウント メジャーに依存する必要があります。 データ ボリュームを減らすためにフィルター処理を行った場合、エラーが減る可能性がありますが、個別の呼び出しとユーザー数でこのエラーの原因を排除できない場合があります。 メジャーが [影響を受け取る通話品質ダッシュボードで使用](dimensions-and-measures-available-in-call-quality-dashboard.md) できるディメンションと寸法を参照してください。


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Skype for Business の CQD データが Teams の CQD データと異なる理由 


> [!IMPORTANT]
> 2020 年 7 月 1 日現在、古い CQD (CQD.lync.com) では最新の CQD (CQD) のデータが使用されます。Teams.microsoft.com)。 古い CQD データは使用できなくなったので、建物やレポートのデータをエクスポートできません。 CQD.lync.com (Skype for Business 管理センターから利用可能) を引き続き使用できますが、まもなく CQD.lync.com へのアクセスがオフになりますので、CQD に移動する必要があります。Teams.microsoft.com まだ行っていない場合は、この設定を行います。


Skype for Business レガシ ポータル (cqd.lync.com) の古い CQD と Teams 管理センター (cqd.teams.microsoft.com) の最新の CQD との間でデータを比較しようとしている場合、データが一致しないのがすぐに分かっています。 これは、最新の CQD レポートで多くの追加の呼び出しシナリオが報告されるからです。 古い CQD のレポートを引き続き使用している場合は、この記事を使用して、これらのレポートを解釈するのに役立ちます [。Skype for Business Server](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)の通話品質ダッシュボード。


  
### <a name="why-cant-i-see-euii-in-cqd"></a>CQD に EUII が表示できない理由

これらの管理者ロールは CQD にアクセスできますが、EUII (エンド ユーザーを特定できる情報) を表示できません。
- Microsoft 365 レポート リーダー
- Teams 通信サポート スペシャリスト

CQD にアクセスできるロール (EUII を含む) の詳細については [、「CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)にアクセスするためにロールを割り当てる」を参照してください。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Teams のみをフィルター処理した場合に、CQD に Skype for Business の情報が表示される理由

CQD レポート (isTeams = 1) でのみ Teams をフィルター処理する場合、第 1 のエンドポイントが Teams であるすべての呼び出 *しをフィルター* 処理します。 第 *2 のエンドポイント* が Skype for Business の場合、その情報が CQD レポートに表示されます。

CQDv2 と CQDv3 では CQDv2 にはない新しいシナリオが作成されるので、CQDv2 と CQDv3 の合計カウントは常に異なります。 これは、集計合計または集計された集計された集計値をフィルターを使って比較すると、期待される違いが生じ得る理由です。  

顧客のシナリオに応じて、CQDv3 には SFB 2019 オンプレミス通話 (SFB 2019 がデータ コネクタで使用されている場合)、Skype ボット通話 (AA、CVI、VDI)、ライブ イベント、PSTN 通話が含まれます。 お客様が利用できるシナリオ/機能ですが、そのデータは CQD V2 に含められません。

たとえば、顧客と 200,000 のオーディオ ストリームが表示され、CQD V2 サマリー レポートで 5000 の失敗が発生すると想定されます。CQD V3 での 300,000 のオーディオ ストリームと 5500 障害 (2019 のオンプレム通話、CVI 通話、PSTN 通話からのストリーム) に対する比較。

予期しない違いがあるかどうかを判断するには、データ全体のさまざまな内訳を確認する必要があります。  目的に合った比較を行います。  ユーザー エージェント カテゴリ ペアによるデータのスライスは、最初に推奨される項目の 1 つです。  *First Product と* *Second Product も* 優れたスライサーです。  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>追加のエントリが必要とわかっているのに、カスタム レポートで返される行数が最大 10,000 行である理由

CQD は集計されたデータ クエリ用に設計され、データ エクスポート用には設計されません。 可能な場合は、10,000 行の制限を超えないように、レポートを再構築することをお勧めします。 まず、月、年、日付、地域、国など、より大きく基数が小さいディメンションを使用して KPI を確認します。そこから、より高い基数のディメンションにドリルダウンできます。 ヘルプデスクとレポートLocation-Enhanced両方とも、このドリルダウン ワークフローの良い例を示します。

## <a name="related-topics"></a>関連項目

[Teams の通話品質の向上と監視](monitor-call-quality-qos.md)

[CQD とは](CQD-what-is-call-quality-dashboard.md)

[通話品質ダッシュボード (CQD) を設定する](turning-on-and-using-call-quality-dashboard.md)

[テナントと建物のデータをアップロードする](CQD-upload-tenant-building-data.md)

[CQD データとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で使用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD でのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)