---
title: "Microsoft Teams での電話会議"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams での電話会議の展開についての実践的なガイダンスを提供します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: d38112015929a3491386146dd0920d81919a8a66
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a>Microsoft Teams での電話会議
=====================================

> [!IMPORTANT]
> 電話会議はパブリック プレビューとして提供されます。 電話会議は、アーリー アダプター (EA) とプレビュー カスタマーを対象とし、リリースまたは更新ごとに変更される場合があります。

Office 365 の電話会議 (旧名: PSTN 会議) では、参加者はどの電話端末からでも会議に参加できます。 Microsoft Teams でも、パブリック プレビューとしてこの機能が利用できるようになりました。ユーザーは自分の電話端末を使用して Teams 会議に参加できます。 この記事の実践的なガイダンスでは、Office 365 FastTrack カスタマーの電話会議の導入フレームワークについて、構想、参加、価値の創出というステップごとに説明します。

Office 365 の[電話会議](https://go.microsoft.com/fwlink/?linkid=858992)で利用できる機能を以下に示します。

> [!NOTE]
> 電話会議は Teams と Skype for Business Online の両方をサポートします。 現時点では、既存の Skype for Business 管理センターとリモート PowerShell で電話会議の管理インターフェースを利用できます。


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

構想 <a name="Envision_AudioConferencing"> </a>
=========

構想の段階は Office 365 カスタマーによる導入の基礎であり、電話会議を含むすべてのワークロードに適用されます。

この段階では、ビジネス目標を明確にするとともに関連するプロジェクト ステークホルダーを編成して、最終的に次のことを実現します。

-   ビジネス ユース ケース、主要ステークホルダー、目的と主要成果 (OKR)、主要成功指標 (KSI)、リスク、環境評価、導入の準備状況、運用計画を含む高度な成功計画。

-   さらに、理想の最終的な状態を実現する、電話会議の詳細な技術実装計画。

<a name="define-business-use-cases-for-audio-conferencing"></a>電話会議のビジネス ユース ケースを定義する
------------------------------------------------

電話会議により、会議の参加者は従来の電話回線、PBX、携帯電話を使用したダイヤルインで PSTN を介して参加できるため、組織は予約済みの会議への追加のエントリ ポイントを確保できます。

これは、開催者や参加者がコンピューターにアクセスしていない場合、データ接続が利用できない場合、モバイル データの対応エリアにムラがあるリモート エリアでの接続や帯域幅が制限された無料の公共 Wi-Fi サービスへの接続など音声通信をサポートするには信頼性が不十分である場合、会議の参加者がすぐに利用できるテレフォニー エンドポイントを使用して会議にダイアルインすることを希望する場合に便利です。

このステップでは、重要なプロジェクト ステークホルダーが電話会議の実装をサポートするビジネス ユース ケースを定義します。

ビジネス ユース ケースは、予期される測定可能なビジネス成果を定義、文書化することを目的としたもので、次の項目を含みます。

-   現在のビジネス プロセスの説明。

-   定義された既存のビジネス プロセスにおける課題。

-   課題の克服に向けたテクノロジーの有効性。

-   課題を克服したときに予期される測定可能なビジネス成果。

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><strong>現在のビジネス プロセスの説明</strong></p>
<p>現在、Contoso 社は地元のテレフォニー プロバイダが提供する PSTN 会議サービスを利用しています。このサービスでは社内会議または外部関係者との会議に対して分単位の料金が発生しています。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><strong>既存のビジネス プロセスにおける課題</strong></p>
<p>Contoso 社は現在の PSTN 会議サービスに対して年間約 100 万ドルを費やしています。これは社内会議で発生するコストの 75％ を占めています。</p>
<p>PSTN 会議サービスによってホストされる従来のテレフォニー エンドポイントを使用した会議への参加は、最新の通信およびコラボレーション プラットフォームとして Teams を導入する組織の計画とは方向性が異なります。</p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><strong>課題の克服に向けたテクノロジーの有効性</strong></p>
<p>Microsoft Teams を最新の通信およびコラボレーション プラットフォームとして導入することで、内部ユーザーは最適なヘッドセットを備えた PC や会議室のデバイスを主に使用して会議に参加することが予測されます。 外部の参加者に対応する場合や、内部の参加者による PC の音声機能の使用が推奨されない状況に対応する場合にも、電話会議サービスを利用することが可能です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><strong>予期される測定可能なビジネス成果</strong></p>
<p>最新の通信およびコラボレーション プラットフォームとして位置付けられた Teams に移行し、電話会議サービスと連携させることにより、Contoso 社は PSTN 会議サービスを提供するためのコストを既存の PSTN 会議サービスの約 20％ にまで年間コストを大幅に削減できることが予期されます。</p></td>
</tr>
</tbody>
</table>

_表 1 ビジネス ユース ケースの例_


このステップで、ビジネス ユース ケースの定義に加え、組織範囲とプロジェクト タイムラインを明確にすることで「構想」段階の次のステップへの移行が容易になります。

<a name="identify-key-stakeholders"></a>主要なステークホルダーを特定する
-------------------------

上記のステップで定義したビジネス ユース ケースには、電話会議の実装についての組織範囲も含まれます。この組織範囲に基づいて、プロジェクトに関与する適任者を編成し、包括的なステークホルダー マトリックスを完成することができます。

<table>
<thead>
<tr class="header">
<th align="left">役割</th>
<th align="left">説明</th>
<th align="left">名前、連絡先情報、場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>プロジェクト エグゼクティブ スポンサー</strong></td>
<td align="left"><ul><li>プロジェクトおよびプロジェクトの目的実現に関する最終的な権限と説明責任</li>
<li>プロジェクト リードによって報告された問題の解決を支援する</li>
<li>社内でのプロジェクトの目標についてのスポンサーとの意思疎通</li>
<li>主要な戦略決定に対する責任</li>
<li>必要なリソースおよび予算の利用可能性に対する責任</p>
<li>主要な四半期ごとのビジネス レビュー (QBR)</li>
<li>啓発キャンペーンの取り組みへの支援とサポート</li>
<li>プログラム ロールアウトのプロジェクト スポンサーとしての役割</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>プロジェクト リード</strong></td>
<td align="left"><ul><li>プロジェクト チームの管理と指導</li>
<li>プロジェクトに関与するパートナーと作業チームを調整する</li>
<li>四半期ごとの主要成果を実現するためのプロジェクト計画の作成と管理に対する責任</li>
<li>部門横断的な課題の解決</li>
<li>プロジェクト スポンサーへの定期的な更新の提供</li>
<li>導入の状況を総合的なプロジェクト計画に取り入れる</li>
<li>月次ビジネスおよび運用レビュー (MBR) の指揮による四半期ごとのビジネス レビューへの貢献</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>コラボレーション リード/アーキテクト</strong></td>
<td align="left"><ul><li>企業の幹部によって定義されたコラボレーション戦略の実行に対する責任</li>
<li>ビジネス目標を満たす企業向けコラボレーション製品の分析と選択</li>
<li>コラボレーション製品の運用設計に対する責任</li>
<li>運用とサポート モデルを定義する</li>
<li>月次および四半期ごとのビジネス レビューのへの貢献</li><ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>コンサルタント</strong></td>
<td align="left"><ul><li>構成サービスに対する責任</li>
<li>全体的なソリューション アーキテクチャに貢献する</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>プロジェクト マネージャー</strong></td>
<td align="left"><ul><li>プロジェクト計画の作成と保守</li>
<li>プロジェクト計画と予算に見合ったプロジェクト成果の管理</li>
<li>報告を含む、プロジェクトの問題の記録と管理</li>
<li>週次スタンド アップ コールの実施</li>
<li>プロジェクト エグゼクティブ スポンサーと連携する、プロジェクト エグゼクティブ スポンサーに更新を提供する</li>
<li>アーキテクトとの協力による変更管理およびコミュニケーション プランの定義</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>変更管理/導入の専門家</strong></td>
<td align="left"><ul><li>検出段階から導入およびトレーニング プロセスへの移行に関する意見を提供する</li>
<li>導入戦略ワークショップに参加する</li>
<li>導入戦略の策定と導入戦略に対する責任</li>
<li>コミュニケーション プランの作成と実行</li>
<li>エンド ユーザーへのトレーニングの提供に対する責任</li>
<li>フィードバックを収集し、調査を実施する</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>ネットワーク リード</strong></td>
<td align="left"><ul><li>検出段階からネットワーク設計への移行に関する意見を提供する</li>
<li>構想ワークショップでの計画作成への参加</li>
<li>プロジェクト実行時のネットワーク チームの作業を調整する</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>セキュリティ リード</strong></td>
<td align="left"><ul><li>検出段階からセキュリティ設計およびプロセスへの移行に関する意見を提供する</li>
<li>構想ワークショップでの計画作成への参加</li>
<li>プロジェクト実行時のセキュリティ チームの作業を調整する</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>テレフォニー リード</strong></td>
<td align="left"><ul><li>検出段階からテレフォニー設計への移行に関する意見を提供する</li>
<li>構想ワークショップでの計画作成への参加</li>
<li>プロジェクト実行時のテレフォニー チームの作業を調整する</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>デスクトップ リード</strong></td>
<td align="left"><ul><li>検出段階からクライアントおよび更新プロセスへの移行に関する意見を提供する</li>
<li>構想ワークショップでの計画作成への参加</li>
<li>プロジェクト実行時のデスクトップ チームの作業を調整する</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>サポート/ヘルプ デスク リード</strong></td>
<td align="left"><ul><li>検出段階から運用およびサポート モデルへの移行に関する意見を提供する</li>
<li>構想ワークショップでの計画作成への参加</li>
<li>サポート モデルの計画への参加</li>
<li>プロジェクト実行時のサポート チーム/リソースの作業を調整する</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>ビジネス ユニットの代表者</strong></td>
<td align="left"><ul><li>エンド ユーザーを対象とした導入ガイドと資料の作成に貢献する</li>
<li>ビジネス ユース ケースへの貢献とレビュー</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>展開リード</strong></td>
<td align="left"><ul><li>展開の前提条件が満たされていることを確認する</li>
<li>準備および展開段階のアクティビティに必要なカスタマー リソースを手配する</li>
<li>準備および展開の状況をレビューする会議に参加する</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>IT 管理者</strong></td>
<td align="left"><ul><li>テストの計画と実施を支援する責任がある IT 専門家</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left"><strong>サービス所有者</strong></td>
<td align="left"><ul><li>電話会議サービス全般の運用に対する責任</li>
<li>電話会議サービスの所有者</li></ul></td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left"><strong>品質チャンピオン</strong></td>
<td align="left"><ul><li>品質、信頼性を向上し、ユーザー フィードバックを促進する</li>
<li>品質の傾向を特定し、該当チームによる修正を促す</li>
<li>運営委員会を介してリーダーシップに報告する</li>
<li>「Rate My Call (通話を評価する)」および「Net Promoter Score (ネット プロモーター スコア)」を使用して品質、信頼性、ユーザーの感想を報告する</li></ul></td>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_表 2 ステークホルダー マトリックス テンプレートの例_


> [!NOTE]
> 上記の例の表およびこのドキュメント内の以降の表はテンプレートとして利用できます。 「TBA」(今後追加される予定) と記載されている箇所には、計画プロセスを遂行する上で満たす必要のある情報が入ります。



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>目的、主要成果、主要成功指標、およびリスクについて定義する
--------------------------------------------------------------------

プロジェクト ステークホルダーの編成が完了すると、ビジネス ユース ケース、組織範囲、プロジェクト タイムラインを目的と主要成果 (OKR) に変換し、プロジェクトの成功の測定方法を主要成功指標 (KSI) の一覧として定義できます。

プロジェクト ステークホルダーは、OKR と KSI の定義に完全に参加することで、プロジェクトに対するオーナーシップを感じることができ、組織のビジネス要件に同調することができます。

OKR には、プロジェクトの開始段階で設定した目的の一覧、四半期ごとに定義した測定可能な主要成果が含まれます。 主要成果は毎月レビューを行ってプロジェクト全体の状況を追跡し、必要な場合は状況に応じて四半期計画を調整することができます。

<table>
<thead>
<tr class="header">
<th align="left"><p><strong>ビジョン</strong>: Office 365 への投資を最大化して生産性を向上</p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>目的</strong></td>
<td align="left"><strong>主要成果</strong></td>
<td align="left"><strong>やるべきこと</strong></td>
</tr>
<tr class="even">
<td align="left">2018 年度末までに Teams での電話会議を展開する</td>
<td align="left">18 年度第 1 四半期: Teams での電話会議をグローバルに展開する</td>
<td align="left"><p>構想</p>
<ul><li>成功計画を作成する</li>
<li>詳細な技術実装計画を作成する</li></ul>
<p>参加</p>
<ul><li>成功計画を実施する</li>
<li>技術実装計画を実施する</li></ul></td>
</tr>
<tr class="odd">
<td align="left">2018 年度半ばまでに旧 PSTN 会議をグローバルで廃止する</td>
<td align="left">18 年度第 2 四半期: 旧 PSTN 会議サービスをグローバルで廃止する</td>
<td align="left"><p>価値の創出</p>
<ul><li>ユーザー エンゲージメントを推進し、導入を促進する</li>
<li>変更の管理と用意を行う</li>
<li>成功を測定、共有して、反復する</li></ul></td>
</tr>
</tbody>
</table>

_表 3 OKR の例_


KSI は主要成果の質と成功を測定し、良い結果と悪い結果を詳細に示すことで OKR に関する 2 つの特性 (達成または未達成) を補足します。 KSI を定義するときには、SMART (具体的な、測定可能な、割り当て可能な、現実的な、適時の ) 条件を使用することをお勧めします。

<table>
<thead>
<tr class="header">
<th align="left">種類</th>
<th align="left"><p>KSI 質問 &amp;</p>
<p>条件</p></th>
<th align="left">測定方法</th>
<th align="left">成功の条件</th>
<th align="left">測定済み</th>
<th align="left">責任</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>使用例/導入</strong></td>
<td align="left">通話の品質は以前のソリューションに比べて同等以上である</td>
<td align="left">アンケート</td>
<td align="left">ユーザーの 80% が同意または強く同意している</td>
<td align="left">有効化後および四半期ごと</td>
<td align="left">情報技術チーム</td>
</tr>
<tr class="even">
<td align="left"><strong>使用例/導入</strong></td>
<td align="left">Teams の導入により通信プロセスが簡易化された</td>
<td align="left">アンケート</td>
<td align="left">ユーザーの 80% が同意または強く同意している</td>
<td align="left">有効化後および四半期ごと</td>
<td align="left">変更管理チーム</td>
</tr>
<tr class="odd">
<td align="left"><strong>使用例/導入</strong></td>
<td align="left">ユーザーが積極的にソリューションを利用している</td>
<td align="left">Office 365 レポート、通話品質ダッシュボード</td>
<td align="left">ユーザーの 80% が毎日使用するアクティブ ユーザーである</td>
<td align="left">毎日</td>
<td align="left">変更管理チーム</td>
</tr>
<tr class="even">
<td align="left"><strong>使用例/品質</strong></td>
<td align="left">低い通話品質/会議品質の割合を最低限に抑える</td>
<td align="left">通話品質ダッシュボード</td>
<td align="left">&lt; 毎月 5% の低品質通話</td>
<td align="left">毎日</td>
<td align="left">情報技術チーム</td>
</tr>
<tr class="odd">
<td align="left"><strong>使用例/サポート</strong></td>
<td align="left">テクニカル サポートの受け方を知っている</td>
<td align="left">アンケート</td>
<td align="left">ユーザーの 90% が同意または強く同意している</td>
<td align="left">有効化後および四半期ごと</td>
<td align="left">変更管理チーム</td>
</tr>
<tr class="even">
<td align="left"><strong>使用例/サポート</strong></td>
<td align="left">テクニカル サポートの品質に満足している</td>
<td align="left">アンケート</td>
<td align="left">ユーザーの 80% が同意または強く同意している</td>
<td align="left">各インシデント後</td>
<td align="left">情報技術チーム</td>
</tr>
<tr class="odd">
<td align="left"><strong>財務</strong></td>
<td align="left">旧会議手段の時間 (分) の削減</td>
<td align="left">財務システム</td>
<td align="left">定義された ROI を達成する</td>
<td align="left">ROI に基づく</td>
<td align="left">変更管理チーム</td>
</tr>
</tbody>
</table>

_表 4 KSI の例_


この演習の一環としてビジネス リスクを特定し、特定した各リスクについて軽減計画を定義する必要があります。 この情報はリスク計画に取り入れることができます。

<table>
<thead>
<tr class="header">
<th align="left">リスク</th>
<th align="left">可能性</th>
<th align="left">影響</th>
<th align="left">全体</th>
<th align="left">軽減計画</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">予定されている合併により最大で 1,000 人の追加が見込まれる</td>
<td align="left">高</td>
<td align="left">高</td>
<td align="left">高</td>
<td align="left"><p>合併される会社については、独自のプロセス (構想、参加、価値の創出) で OKR を分離する</p>
<p>既存の OKR に含めない</p></td>
</tr>
<tr class="even">
<td align="left">電話番号の移行のためプロジェクトの完了が遅れる</td>
<td align="left">高</td>
<td align="left">高</td>
<td align="left">高</td>
<td align="left"><p>電話番号の移行をサポートするために必要なすべての情報 (カスタマー サービス レコード、請求書の詳細、承認状など) を事前に用意する</p>
<p>電話番号の移行の所要時間に対応するためプロジェクト タイムラインを調整する</p>
<p>新しいダイヤルイン会議番号の使用を外部の参加者に伝える</p></td>
</tr>
<tr class="odd">
<td align="left">計画されたネットワーク再設計</td>
<td align="left">高</td>
<td align="left">中</td>
<td align="left">中</td>
<td align="left">最新の通信およびコラボレーション プラットフォームとして Teams を実装する前に、プロジェクトの範囲においてサイトに対する Network Readiness Assessment を実行します。</td>
</tr>
</tbody>
</table>

_表 5 リスク計画の例_


<a name="assess-environment-and-evaluate-adoption-readiness"></a>環境の評価と、導入の準備状況の評価を行う
--------------------------------------------------

設定した OKR を達成するため、ソリューションの高度アーキテクチャを定義しなければならない場合があります。 その場合は、環境を検出して、IT とテレフォニーのインフラストラクチャ、ネットワーキング、運用に関連するすべての側面を評価します。

環境の検出には、電話会議のビジネス ユース ケースをサポートするための PC およびモバイル デバイスの準備状況 (ハードウェア要件からソフトウェア要件まで) の評価など、エンドユーザー コンピューティングに関連するすべての事項が含まれます。

環境の検出では、[電話番号を Microsoft に移行する](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e)必要があるかどうかも明らかになります。 これによって、組織は必要性の有無に応じてプロジェクト計画を調整し、番号の移行に必要な情報を準備することができます。 次の[アンケート](https://go.microsoft.com/fwlink/?linkid=858995)を活用して環境の検出を行うことができます。

環境の検出では、Network Readiness Assessment を実行して、電話会議サービスの実装をサポートする準備がネットワークで整っているかを確認する必要があります。

電話会議サービスをサポートするためのネットワークの準備状況は、環境の検出で [My Advisor Network Planner ツール](https://go.microsoft.com/fwlink/?linkid=858999) に取得した情報 (インターネット接続性や WAN トポロジ、サイト リンク、利用可能な帯域幅、ペルソナ分析データ (各ワークロードについて予期される使用方法に変換可能)) を活用して判断できます。 ネットワークの準備状況をさらに深く確認する場合は、[Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) または [Network Readiness Assessment ツール パートナー](https://go.microsoft.com/fwlink/?linkid=859003)によって提供されるソリューションを使用してリアルタイムのメディア トラフィック シミュレーションを行うことができます。

Network Readiness Assessment の結果により、必要なネットワーク最適化、または電話会議の実装を成功させるために必要な修復が明確になります。

導入の準備状況は、ペルソナ分析を行い、電話会議サービスの実装の対象とする組織内のペルソナの一覧を作成することで評価できます。 ペルソナ分析には、設定したビジネス成果を実現するために必要な追加の周辺機器やデバイスの特定も含まれます。

ペルソナ分析を行う場合は、[Persona Alignment (ペルソナ調整)](https://go.microsoft.com/fwlink/?linkid=859005) ワークショップ デッキと [Persona Feature Matrix (ペルソナ機能マトリックス)](https://go.microsoft.com/fwlink/?linkid=859006) を活用して関連するプロジェクト ステークホルダーが参加するワークショップを開催できます。 ペルソナ分析ワークショップの結果は [Persona Analysis Report (ペルソナ分析レポート)](https://go.microsoft.com/fwlink/?linkid=859007) テンプレートを使用してレポートにまとめることができます。


> [!NOTE]
> Discovery Questionnaire (検出アンケート) と Persona Analysis (ペルソナ分析)の例は Skype for Business Online 用に作成されたものですが、その内容の大部分は Teams にも関連します。 プロジェクトの目標に関連しない項目は自由に変更または削除してください。


環境の評価と導入の準備状況の評価の一環として、技術的なリスクを特定し、特定した各リスクについて軽減計画を作成することができます。 この情報はリスク計画の一部として取り入れる必要があります。

<a name="map-operational-roles"></a>運用の役割をマッピングする
---------------------

最初のパイロット ユーザーを有効にした時点で運用を開始する必要があるため、運用の計画と電話会議サービスを運用するチームの特定は重要なステップです。 特定された各チームは、指定されたタスクと責任を確認して同意し、電話会議サービスを運用するための準備に取りかかる必要があります。 この準備には、トレーニングや用意、スタッフの追加、サービスを提供するために必要な外部プロバイダの設定などが含まれます。

<table>
<thead>
<tr class="header">
<th align="left">運用の役割</th>
<th align="left">説明</th>
<th align="left">チーム</th>
<th align="left">連絡先の詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">サービス所有者</td>
<td align="left">サービス所有者、ビジネス部門へのインターフェース、戦略</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">電話会議の運用</td>
<td align="left">日常的な運用、ユーザーとデバイス アカウントの移動/追加/変更、監視</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">テナント管理者</td>
<td align="left">テナント全体の設定の変更、新しい機能の有効化</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">ヘルプ デスク</td>
<td align="left">エンドユーザーがサポートを受けるためのインターフェース</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">ネットワークの運用</td>
<td align="left">LAN、WAN、Wi-Fi、インターネット アクセスを実装する</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">Client &amp; Endpoints チーム</td>
<td align="left">デスクトップの展開を管理する</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">ID の運用</td>
<td align="left">ID インフラストラクチャを管理する (AD、ADFS、Azure AD)</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="even">
<td align="left">導入/変更管理</td>
<td align="left">ソリューションの啓発、トレーニング、導入を管理する</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
<tr class="odd">
<td align="left">Exchange の運用</td>
<td align="left">Exchange 環境を管理する</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_表 6 運用の役割のマッピングの例_


運用の役割のマッピングを、各役割に関するタスクの情報を含むより詳細なものにする場合は、[Operational Role Mapping Workbook (運用の役割マッピング ワークブック)](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) を使用すると、電話会議サービスをサポートするための役割と責任を明確にする詳細な情報を得ることができます。

<a name="document-success-plan"></a>成功計画を文書化する
---------------------

成功計画は構想段階で作成する文書で、ビジネス ケース、サービスの準備状況、導入計画、運用計画で構成されます。

成功計画は、FastTrack や展開パートナーを含むプロジェクト チームに対して、電話会議サービスにより組織の目標を実現する上で十分な情報を提供します。

一般的に、成功計画は以下の主なセクションで構成されます。

-   ビジネス ケース

-   サービスの準備状況

-   導入計画

-   運用計画

### <a name="business-case"></a>ビジネス ケース

一般的に、ビジネス ケースに必要な主な情報には、ビジネス ユース ケース、ステークホルダー、OKR と KSI、リスク、プロジェクト タイムラインがあります。 成功計画の一部として、こうした情報を文書化する必要があります。

### <a name="service-readiness"></a>サービスの準備状況

環境の評価では、電話会議の実装に向けた組織の技術的な準備状況を判断するために必要な初期情報が提供されます。

ここでは、環境の評価で検出された、修復が必要な領域に対処する計画も示されます。 成功計画の一部としてサービスの準備状況の評価と修復計画を含める必要があります。

### <a name="adoption-plan"></a>導入計画

導入の準備状況の評価に続き、より詳細な計画を完成させて、プロジェクト チームが通信計画、トレーニング計画、立ち上げ前/立ち上げ時/立ち上げ後に関する包括的な導入アクティビティを導き出せるようにする必要があります。

このステップでは、チラシ、ウェルカム メール、トレーニング資料といった導入アクティビティをサポートするリソースを特定し、さらに組織の要件を満たすために必要なカスタマイズを特定します。

導入アクティビティのテンプレートは[こちら](https://www.microsoft.com/download/details.aspx?id=54244)で入手できます。

### <a name="operational-plan"></a>運用計画

運用の役割のマッピングに関する演習では、役割と責任、電話会議の実装をサポートする運用の各役割に割り当てるチームを決定します。

ソリューションの運用準備を確実に行うため、この作業を完了させて、成功計画の一部として運用計画を含める必要があります。

Teams での電話会議の計画  <a name="Planning_AudioConferencing"> </a>
========================================

Teams での電話会議の実装を計画するには、ビジネス要件を満たすソリューションの実装に向けて組織が十分な準備を行うことができるよう、事前に一連の意思決定を行う必要があります。 この意思決定は技術実装計画で文書化します。

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a>電話会議の利用可否

電話会議は以下の[国と地域](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US)で利用できます。


> [!IMPORTANT]
> 法的な規制により、多国間組織での電話会議の利用には、電話会議サービスが提供されている国や地域から Office 365 サブスクリプションの契約が提供される必要があります。

組織が電話会議サービスの利用資格を有していることが確認できたら、利用可能な国と地域のリストに基づいて、電話会議サービスを実装するユーザーの場所やオフィスのリストを作成します。

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">判断ポイント</td>
<td align="left"><p>電話会議サービスを実装するユーザーの場所またはオフィスを決定します。</p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">次のステップ</td>
<td align="left"><p>電話会議サービスを有効にするユーザーの場所とオフィスを文書化します。</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">オフィス</th>
<th align="left">場所</th>
<th align="left">PSTN 会議サービス</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">One Epping Road</td>
<td align="left">オーストラリア</td>
<td align="left">電話会議</td>
</tr>
<tr class="even">
<td align="left">100 Cyberport Road</td>
<td align="left">香港特別自治区</td>
<td align="left">旧 PSTN 会議</td>
</tr>
<tr class="odd">
<td align="left">One Marina Boulevard</td>
<td align="left">シンガポール</td>
<td align="left">電話会議</td>
</tr>
<tr class="even">
<td align="left">32 London Bridge Street</td>
<td align="left">イギリス</td>
<td align="left">電話会議</td>
</tr>
<tr class="odd">
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">フランス</td>
<td align="left">電話会議</td>
</tr>
</tbody>
</table>

_表 7 電話会議サービス サイト有効化リストの例_


## <a name="licensing-for-audio-conferencing"></a>電話会議のライセンス

[電話会議ライセンス](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US) (旧名: Skype for Business PSTN 会議ライセンス) は、Office 365 E5 サブスクリプション プランの一部、または Office 365 E1 や Office 365 E3 サブスクリプション プランへのアドオンとして利用できます。

> [!NOTE]
> Teams での PSTN またはダイヤルイン会議は、サードパーティ<sup></sup>の電話会議プロバイダー (ACP) をサポートしません。<br>Skype for Business Online PSTN 会議を使用している場合は、Teams ですぐに電話会議を利用できます。

無料電話の会議ブリッジ電話番号を提供したり、国際電話番号への会議ダイヤルアウトをサポートするには、組織の[通信クレジット](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059)を設定する必要があります。


> [!IMPORTANT]
> 一部の国では通話無料の会議ブリッジ電話番号でのみサービスが提供されます。こうした国でダイヤルインをサポートするには、通信クレジットの使用が必須になります。

通信クレジットを実装するには、最初に初回購入金額を決定します。 推奨される金額については、[Communications Credits (通信クレジット)](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) のドキュメントを参照してください。

[Communications Credits (通信クレジット)](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) のドキュメントには、組織が自動リチャージを使用する場合のリチャージ実行 (資金の最小金額) の推奨金額も記載されています。 自動リチャージの金額は実際の使用量に応じて決定する必要があります。 通信クレジットの使用量を経時的に監視して、必要に応じてリチャージの金額を調整する必要があります。

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">判断ポイント</td>
<td align="left"><ul><li>組織が必要な電話会議ライセンスをまだ購入していない場合は、電話会議ライセンスの取得方法を既存の Office 365 サブスクリプションからステップ アップするか、電話会議アドオンを入手するかのいずれかに決定します。</li>
<li>電話会議の実装で通信クレジットが必要であるかどうかを決定します。 必要な場合は、初回購入金額を決定します。 該当する場合は、リチャージを実行する金額と自動リチャージする金額を決定します。</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">次のステップ</td>
<td align="left"><ul><li>電話会議ライセンスを割り当てるユーザーを文書化します。</li>
<li>通信クレジット計画 (初回購入金額、リチャージを実行する金額、自動リチャージする金額) を文書化します。</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">ユーザー</th>
<th align="left">オフィス</th>
<th align="left">Office 365 ライセンス</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E3、電話会議アドオン</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E3、電話会議アドオン</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E3、電話会議アドオン</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E3、電話会議アドオン</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E3、電話会議アドオン</td>
</tr>
</tbody>
</table>

_表 8 電話会議の開催者のライセンス割り当てリストの例_

<table>
<thead>
<tr class="header">
<th align="left">初回購入金額</th>
<td align="left">$ 1,000</td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left">リチャージを実行する金額</th>
<td align="left">$400</td>
</tr>
<tr class="header">
<th align="left">自動リチャージする金額</th>
<td align="left">TBA</td>
</tr>
</tbody>
</table>

_表 9 通信クレジットの計画番号の例_


## <a name="conference-bridge-phone-numbers"></a>会議ブリッジ電話番号

Office 365 の電話会議サービスには次が含まれます。

-   複数の種類の会議ブリッジ電話番号 (有料電話と無料電話)

-   複数のカテゴリの電話番号 (専用と共有)

-   会議ブリッジでの複数言語のサポート (プライマリとセカンダリ)

-   テナントの既定の電話番号

提供される機能の詳細な説明については、「[Skype for Business のダイヤルインまたは PSTN 会議をセットアップする](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US)」と「[ダイヤルイン会議の電話番号](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)」**をご覧ください。**

> [!NOTE]
> 専用の会議ブリッジ電話番号は、「[Skype for Business サービスの電話番号を取得する](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734)」で説明されている適用可能なライセンス数に応じた、テナントごとに取得可能な電話番号の制限にカウントされます。 無料電話の会議ブリッジ電話番号では通信クレジットが必要になります。

電話会議サービスに移行する必要のある既存の会議ブリッジ電話番号が存在する場合は、国固有の要件を満たしているという前提の上で既存の会議ブリッジ電話番号を Microsoft に移行できます。


> [!NOTE]
> Microsoft への電話番号の移行における複雑さは、国や地域、キャリヤ、関与する回路の数、その他多くの関連する要因によって大きく左右されます。 電話番号の移行を計画する場合は、「[Number Porting Guide (番号の移行ガイド)](https://go.microsoft.com/fwlink/?linkid=859011)」を参照してください。

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

電話会議サービスへの電話番号の移行について詳しくは、「[Transfer phone numbers to Skype for Business Online (Skype for Business Online への電話番号の移行)](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e)」をご覧ください。

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">判断ポイント</td>
<td align="left"><ul><li>組織で専用の会議ブリッジ電話番号が必要かどうかを決定します。</li>
<li>電話会議の実装においてユーザーの場所またはオフィスに対して会議ブリッジ電話番号を取得する方法 (Microsoft から取得または既存の電話番号の移行) を決定します。</li>
<li>Microsoft から取得する場合は、電話会議の実装の範囲内のユーザーの場所またはオフィスに対して電話番号を取得する方法 (フォーム提出または自動) を決定します。</li>
<li>それぞれの専用会議ブリッジ電話番号に設定する言語設定を決定します。</li>
<li>テナントの既定の会議ブリッジ電話番号を決定します。</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">次のステップ</td>
<td align="left"><ul><li>電話会議の実装の範囲内のそれぞれのユーザーの場所またはオフィスに対して電話番号を取得する方法を詳しく記述する電話番号取得のマスタープランを文書化します。</li>
<li>該当する場合は、場所またはオフィスごとに <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">New Telephone Number Request (新規電話番号要求)</a> フォームを入力します。</li>
<li>既存の電話番号を移行する場合は、「<a href="https://go.microsoft.com/fwlink/?linkid=859011">Number Porting Guide (番号の移行ガイド)</a>」を参照して、電話会議の実装タイムラインを調整してください。</li>
<li>詳細な会議ブリッジ番号構成 (共有および専用の会議ブリッジ電話番号、それぞれの専用会議ブリッジ電話番号の言語設定、テナントの既定の会議ブリッジ電話番号) を文書化します。</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">オフィス</th>
<th align="left">ブリッジ番号の取得とブリッジの種類</th>
<th align="left">ブリッジ番号</th>
<th align="left">ブリッジの言語</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">One Epping Road</td>
<td align="left">新規に取得、専用</td>
<td align="left">TBA</td>
<td align="left">英語 (オーストラリア)</td>
</tr>
<tr class="even">
<td align="left">One Marina Boulevard</td>
<td align="left">新規に取得、共有</td>
<td align="left">TBA</td>
<td align="left">英語 (米国)、中国語 (簡体字、PRC)</td>
</tr>
<tr class="odd">
<td align="left">32 London Bridge Street</td>
<td align="left">既存のポート、専用</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">英語 (英国)</td>
</tr>
<tr class="even">
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">新規に取得、専用</td>
<td align="left">TBA</td>
<td align="left">フランス語 (フランス)、英語 (英国)</td>
</tr>
</tbody>
</table>

_表 10 会議ブリッジの詳細の例_


> [!NOTE]
> 上記の例の表およびこのドキュメント内の以降の表はテンプレートとして利用できます。 「TBA」(今後追加される予定) と記載されている箇所には、計画プロセスを遂行する上で満たす必要のある情報が入ります。

## <a name="conference-bridge-settings"></a>会議ブリッジの設定

電話会議への参加に関する操作と表示 (会議の参加および退出に関する通知、発信者名の記録)、会議の開催者の PIN の長さ、電子メール通知といった組織全体の構成オプションをエンドユーザーのエクスペリエンスに応じて細かく調整できます。

-   会議の参加と退出に関する通知は、記録された名前、電話番号、効果音の形式で利用できます。

-   PIN の長さは 4～12 桁です。既定は 5 桁の PIN です。

-   電話会議ライセンスが有効になるときや、管理者による変更時に送信される通知メールは、既定で有効になります。 この機能は無効にすることができます。無効にすることで組織のエンドユーザーの通信を制御できます。

電話会議ライセンスが割り当てられたユーザーの場合、電話会議の調整に表示される既定の有料/無料電話番号は次のいずれかに構成して使用できます。

-   テナントレベルの既定の番号

-   自動的に割り当てられる会議ブリッジ電話番号

-   各ユーザーに対して手動で定義する会議ブリッジ電話番号

通常、ユーザー固有の会議ブリッジ電話番号は、ユーザーが地理的に分散され、会議の招待状に既定の会議ブリッジ電話番号として市内番号を指定する必要がある国際的または全国的な組織にとって便利です。

他の都市や海外から参加する参加者は、テナントレベルで構成された追加の番号を検索することができます。ただし、この番号は会議の招待状には直接表示されません。 会議の招待状には、参加者を [Teams Conference Dial-in Numbers (Teams の会議ダイヤルイン番号)] ページに導くリンクが記載されています。このページでは、参加者の場所から最も近い会議ブリッジ電話番号を検索することができます。

さらに、会議の各開催者は未認証の発信者の処理方法を構成することもできます。未認証の発信者の参加を許可する前に開催者が会議を開始する必要があるかどうか、会議を開始する当たって開催者が未認証の発信者を許可する必要があるかどうかを構成できます。

各ユーザーに適用可能な追加の構成を使用して、無料電話の会議ブリッジ電話番号の使用や会議からのダイヤルアウトを制御できます。

> [!NOTE]
> 現時点では、料金に関連するこれらの制御はプレビュー カスタマーのみが利用できます。 組織は [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013) でプレビュー プログラムに登録できます。

これらの制御を使用すると、会議の開催者は開催する会議で無料電話の会議ブリッジ電話番号を提供するかどうかを決めたり、参加者が会議からダイヤルアウトできるかどうかを制御したりすることができます。 ダイヤルアウトの制御には、ダイヤルアウトの禁止、国内番号にのみダイヤルアウトを許可、国内および国際番号の両方にダイヤルアウトを許可があります。

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">判断ポイント</td>
<td align="left"><ul><li>組織で会議の参加と退出の通知が必要かどうかを決定し、必要な場合は実装する通知の種類 (効果音、電話番号または記録された名前) を決定します。</li>
<li>組織のセキュリティ要件に合った電話会議の PIN の長さを決定します。</li>
<li>組織で電話会議サービスに関連するエンドユーザーの通信を制御するかどうかを決定します。</li>
<li>会議ブリッジ電話番号を各会議の開催者に割り当てるかどうかを決定します。</li>
<li>一部の会議の開催者について、会議に無料電話の会議ブリッジ電話番号の使用が必要かどうかを決定します。</li>
<li>一部の会議の開催者について、会議を開始する前に未認証の発信者を許可する機能が必要かどうかを決定します。</li>
<li>一部の会議の開催者について、会議ダイヤルアウトを制御する機能が必要かどうかを決定します。</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">次のステップ</td>
<td align="left"><ul><li>詳細な会議ブリッジ設定 (参加および退出の通知、PIN 長さ、構成変更メール通知) を文書化します。</li>
<li>各会議の開催者に割り当てる会議ブリッジ電話番号、さらに未認証の発信者のポリシー、無料電話、ダイヤルアウトの制御に対する設定を文書化します。</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><strong>会議の参加および退出の通知を有効にする</strong></td>
<td align="left">有効</td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><strong>参加/退出のアナウンスのタイプ</strong></td>
<td align="left">効果音</td>
</tr>
<tr class="header">
<td align="left"><strong>会議に参加する前に名前を記録するように発信者に求める</strong></td>
<td align="left">無効</td>
</tr>
<tr class="header">
<td align="left"><strong>PIN の長さ</strong></td>
<td align="left">5</td>
</tr>
<tr class="header">
<td align="left"><strong>ユーザーのダイヤルイン設定の変更時にそのユーザーに自動的にメールを送信する</strong></td>
<td align="left">無効</td>
</tr>
</tbody>
</table>

_表 11 会議ブリッジ設定の例_


<table>
<thead>
<tr class="header">
<th align="left">ユーザー</th>
<th align="left">オフィス</th>
<th align="left">既定の有料電話番号</th>
<th align="left">既定の無料電話番号</th>
<th align="left">無料電話を許可する</th>
<th align="left">未認証の発信者のバイパス ロビー</th>
<th align="left">会議ダイヤルアウト</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">はい</td>
<td align="left">有効</td>
<td align="left">国際および国内</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">いいえ</td>
<td align="left">無効</td>
<td align="left">許可されていない</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">いいえ</td>
<td align="left">無効</td>
<td align="left">許可されていない</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">はい</td>
<td align="left">無効</td>
<td align="left">国内</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">はい</td>
<td align="left">有効</td>
<td align="left">国内</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">はい</td>
<td align="left">有効</td>
<td align="left">国内</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">はい</td>
<td align="left">有効</td>
<td align="left">許可されていない</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">はい</td>
<td align="left">無効</td>
<td align="left">許可されていない</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">TBA</td>
<td align="left">はい</td>
<td align="left">無効</td>
<td align="left">許可されていない</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">いいえ</td>
<td align="left">無効</td>
<td align="left">国内</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">はい</td>
<td align="left">有効</td>
<td align="left">国際および国内</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">TBA</td>
<td align="left">TBA</td>
<td align="left">いいえ</td>
<td align="left">無効</td>
<td align="left">国内</td>
</tr>
</tbody>
</table>

_表 12 会議ブリッジ設定の割り当ての例_


## <a name="dial-plans"></a>ダイヤル プラン

Office 365 の電話システム機能である[ダイヤル プラン](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b)は、通話の認証およびルーティングの目的で、ダイヤルされた電話番号を代替形式 (通常、[E.164](https://go.microsoft.com/fwlink/?linkid=859014) 形式) に変換する正規化ルールです。 電話会議サービスは、この電話システムで使用されるものと同じ機能を使用して、会議ダイヤルアウトのシナリオでダイヤルされた電話番号を変換します。

ダイヤル プランでは、ユーザーは従来の使い慣れた方法で電話番号をダイヤルできます (市内通話の場合に市外局番を省略、国内通話の場合に国番号を省略、会議ダイヤルアウト実行時に短い桁をダイヤル)。

Office 365 の電話システム機能には、次の 2 種類のダイヤル プランがあります。

-   **サービス ダイヤル プラン**: 既定のダイヤル プランで、Office 365 の使用場所に基づいてユーザーに適用されます。変更することはできません。

<!-- -->

-   **テナント ダイヤル プラン**: テナント内のカスタマイズ可能なダイヤル プランです。さらに 2 つのタイプに分類されます。

    -   **テナント - グローバル ダイヤル プラン** - テナント内のすべてのユーザーに適用されるダイヤル プラン。

    -   **テナント - ユーザー ダイヤル プラン** - 特定のユーザーにのみ適用されるダイヤル プラン。


> [!NOTE]
> 詳細と例については、「[Office 365 Calling Plan dial plans (Office 365 通話プランのダイヤル プラン)](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b)」をご覧ください。

ユーザーに有効なダイヤル プランを割り当てるには、サービス ダイヤル プラン (ユーザーが Office 365 を使用する場所に基づく) とテナント ダイヤル プラン (テナント - グローバル ダイヤル プランまたはテナント - ユーザー ダイヤル プランのいずれか) を組み合わせます。

![サービス ダイヤル プランとテナント ダイヤル プランの 3 つの組み合わせを表に示します。](media/audio_conferencing_image8.png)

各テナント ダイヤル プランには最大で 25 の正規化ルールがあります。このため、サービス ダイヤル プランの一部として既に利用可能な正規化ルールとの重複を回避する必要があります。

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">判断ポイント</td>
<td align="left"><ul><li>カスタマイズしたダイヤル プラン (ビジネス要件、導入要件など) が組織で必要かどうかを決定します。</li>
<li>該当する場合は、カスタマイズしたダイヤル プランの要件を満たすテナント ダイヤル プランの範囲 (テナント - グローバルまたはテナント - ユーザー) を決定します。</li>
<li>該当する場合は、電話会議の実装の範囲内のユーザーの場所とオフィスをサポートするために作成するテナント ダイヤル プランを決定します。</li>
<li>該当する場合は、カスタマイズしたダイヤル プランが必要なユーザー、各ユーザーに割り当てるテナント ダイヤル プランを決定します。</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">次のステップ</td>
<td align="left"><ul><li>カスタマイズしたダイヤル プランと、電話会議の実装の一環として構成される関連した正規化ルールを文書化します。</li>
<li>カスタマイズしたダイヤル プランが必要なユーザー、各ユーザーに割り当てるテナント ダイヤル プランを文書化します。</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">テナント ダイヤル プランの名前/説明</th>
<th align="left">正規化ルールの名前/説明</th>
<th align="left">パターン</th>
<th align="left">変換</th>
<th align="left">IsInternalExtension</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>AU-NSW-NorthRyde-OER</strong></p>
<p><em>One Epping Road North Ryde、NSW、AU ダイヤル プラン</em></p></td>
<td align="left"><p><strong>AU-NSW-NorthRyde-OER-Internal</strong></p>
<p><em>One Epping Road オフィスの内部番号 (x7000 - x7999)、North Ryde、NSW、オーストラリア</em></p></td>
<td align="left">^(7\d{3})$</td>
<td align="left">+6125550$1</td>
<td align="left">True</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>AU-NSW-Local</strong></p>
<p><em>NSW、オーストラリアの市内番号の正規化</em></p></td>
<td align="left">^([2-9]\d{7})$</td>
<td align="left">+612$1</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>AU-TollFree</strong></p>
<p><em>オーストラリアの無料電話番号の正規化</em></p></td>
<td align="left">^(1[38]\d{4,8})\d*$</td>
<td align="left">+61$1</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>AU-Service</strong></p>
<p><em>オーストラリアのサービス番号の正規化</em></p></td>
<td align="left">^(000|1[0125]\d{1,8})$</td>
<td align="left">$1</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SG-Singapore-OMB</strong></p>
<p><em>OMB Singapore、SG ダイヤル プラン</em></p></td>
<td align="left"><p><strong>SG-OMB-Internal</strong></p>
<p><em>OMB オフィスの内部番号 (x8000 – x8999)、シンガポール</em></p></td>
<td align="left">^(8\d{3})$</td>
<td align="left">+656888$1</td>
<td align="left">True</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>SG-TollFree</strong></p>
<p><em>シンガポールの無料電話番号の正規化</em></p></td>
<td align="left">^(1?800\d{7})\d*$</td>
<td align="left">+65$1</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>SG-Service</strong></p>
<p><em>シンガポールのサービス番号の正規化</em></p></td>
<td align="left">^(1\d{3,4}|9\d{2})$</td>
<td align="left">$1</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"><p><strong>FR-Paris-Issy-39qdPR</strong></p>
<p><em>39 quai du Président Roosevelt Issy-les-Moulineaux、フランスのダイヤル プラン</em></p></td>
<td align="left"><p><strong>FR-39qdPR-Internal</strong></p>
<p><em>39 quai du Président Roosevelt オフィスの内部番号 (x7000 – x7999)、Issy-les-Moulineaux、フランス</em></p></td>
<td align="left">^(7\d{3})$</td>
<td align="left">+3319999$1</td>
<td align="left">True</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>FR-TollFree</strong></p>
<p><em>フランスの無料電話番号の正規化</em></p></td>
<td align="left">^0?(80\d{7})\d*$</td>
<td align="left">+33$1</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>FR-Service</strong></p>
<p><em>フランスのサービス番号の正規化</em></p></td>
<td align="left"><p>^(1\d{1,2}|11[68]\d{3}|</p>
<p>10\d{2}|3\d{3})$</p></td>
<td align="left">$1</td>
<td align="left">False</td>
</tr>
</tbody>
</table>

_表 13 テナント ダイヤル プランの例_


<table>
<thead>
<tr class="header">
<th align="left">ユーザー</th>
<th align="left">オフィス</th>
<th align="left">ダイヤル プランの種類</th>
<th align="left">ダイヤル プランの名前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">テナント ダイヤル プラン</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">テナント ダイヤル プラン</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">テナント ダイヤル プラン</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">テナント ダイヤル プラン</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">テナント ダイヤル プラン</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">テナント ダイヤル プラン</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">サービス ダイヤル プラン</td>
<td align="left">該当なし</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">サービス ダイヤル プラン</td>
<td align="left">該当なし</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">サービス ダイヤル プラン</td>
<td align="left">該当なし</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">テナント ダイヤル プラン</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">テナント ダイヤル プラン</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">テナント ダイヤル プラン</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
</tbody>
</table>

_表 14 ダイヤル プランの割り当ての例_


## <a name="microsoft-teams-configurations"></a>Microsoft Teams の構成

電話会議は予約済みの会議にのみ利用できるため、会議の予約 (プライベート会議およびチャネル会議) を制御するテナントレベルの構成を有効にする必要があります。


> [!NOTE]
> すべての会議のディスカッションを検出可能にするというコンプライアンス要件が組織に対して課せられている場合、会議の開催者が Exchange オンプレミス メールボックスを利用しているならば、プライベート会議を無効にすることをお勧めします。<br><br>
> 組織のすべての会議が<strong>招待されたユーザー</strong>にのみ表示される必要がある場合は、<strong>チャネル</strong>で会議を予約する機能を無効にして、招待されていないユーザーに情報が公開されないようにすることをお勧めします。

テナントレベルの構成の一部であるこれらの設定は、組織のすべてのユーザーに適用され、電話会議を**使った** Teams の会議だけでなく、Teams でのすべての会議の予約に影響を及ぼします。

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">判断ポイント</td>
<td align="left"><p>組織でプライベート会議の予約を有効または無効にする必要があるかどうかを決定します。</p>
<p>組織でチャネル会議の予約を有効または無効にする必要があるかどうかを決定します。</p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">次のステップ</td>
<td align="left"><p>Teams の会議予約の構成を文書化します。</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><strong>プライベート会議の予約を許可する</strong></td>
<td align="left">有効</td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><strong>チャネル会議の予約を許可する</strong></td>
<td align="left">無効</td>
</tr>
</tbody>
</table>

_表 15 Microsoft Teams の会議の構成の例_


## <a name="document-technical-implementation-plan"></a>技術実装計画を文書化する

上記の判断ポイントを参考にして、技術実装計画を文書化します。

この技術実装計画は、FastTrack または展開パートナーを含むプロジェクト チームに対して、電話会議の実装における技術面での参加を行うために必要な情報を提供します。

一般的に、技術実装計画は以下の主なセクションで構成されます。

-   電話会議サービス サイト有効化リスト

-   電話会議の開催者のライセンス割り当てリスト

-   通信クレジットの計画番号

-   会議ブリッジの詳細

-   会議ブリッジの設定

-   会議ブリッジの設定の割り当て

-   テナント ダイヤル プラン

-   ダイヤル プランの割り当て

-   Microsoft Teams の会議の構成

成功計画と技術実装計画を完成することにより、組織では Office 365 カスタマーの次の導入ステップに進む準備が整います。

<a name="onboard"></a>参加
=======

*準備中*

<a name="drive-value"></a>価値の創出
===========

*準備中*



### <a name="see-also"></a>関連項目
[Skype for Business のダイヤルインまたは PSTN 会議をセットアップする](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)
