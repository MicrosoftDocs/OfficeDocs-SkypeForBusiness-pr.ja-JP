---
title: "Skype for Business と共存する Microsoft Teams を有効にする"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "共存する Skype for Business と Microsoft Teams の使用に関するガイダンス"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: b1a635fe4abb607064a0e26240ed58715fa43a8d
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2017
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a>Skype for Business と共存する Microsoft Teams を有効にする 
=============================================================

既に Skype for Business Online が展開されている組織にとって、最近発表された Microsoft Teams は単独の通信/コラボレーション ソリューションとしての Teams の潜在力を評価する機会を提供するものです。同時に、組織は 2 つのソリューションのどちらを重視するか、環境においてそれらをどのように共存できるか、ということについて難しい判断をすることになります。

Teams が現在のビジネス要件を満たす場合は、組織における単一の通信/コラボレーション ソリューションとして Teams の導入を開始することができます。

既定では、Teams は資格あるすべてのテナントで有効になります。 したがって、Skype for Business と共存する形で Teams を管理する方法を決定し、ユーザーの期待に応える取り組みを行う必要があります。

通常、共存の環境ではカスタマーによる 2 つの導入方法があります。 導入方法は次のとおりです。

-   **オプション 1:** 管理下にない共存での導入

    IT は共存のエクスペリエンスを積極的に制御しないため、ユーザーは好みのアプリを選択できます。

-   **オプション 2:** 管理下にある共存での導入

    IT は、ユーザーに対して Team を段階的に紹介することで共存のエクスペリエンスを制御します。最初に Teams でのプライベート チャット、次に会議のエクスペリエンス、最後に通話のエクスペリエンスというように段階的に新しいチャットベースのコラボレーション ワークスペースを導入します。

![共存環境でのカスタマーによる 2 つの導入方法の図: 管理下と非管理下](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a>共存の利点と考慮事項
----------------------------------------

それぞれの移行では、組織の概要に基づいて正しい移行パスを決定するために利点と考慮事項を評価する必要があります。 次の表に、共存の環境におけるカスタマーによる移行について、非管理下と管理下の比較を示します。


<table>
<thead>
<tr class="header">
<th align="left">移行パス</th>
<th align="left">管理下にない共存</th>
<th align="left">管理下にある共存</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>組織概要</strong></td>
<td align="left"><ul>
<li>通常、専用の IT リソースのない小規模の組織</li>
<li>IT は作業に適したツールの選択をユーザーの裁量にゆだねる</li>
<li>主な Skype for Business の使用法は IM/P と会議</li>
</ul></td>
<td align="left"><ul><li>通常、中規模から大規模の組織</li>
<li>IT が新しいツールのロールアウトをより積極的に制御することを希望している</li>
<li>Skype for Business の導入を深める</li>
<li>ネットワークとインフラストラクチャの複雑性の増加</li>
<li>複数の場所</p>
<li>独自の UC 機能を持つ単一アプリの選択</li></ul></td>
</tr>
<tr class="even">
<td align="left"><strong>利点</strong></td>
<td align="left"><ul>
<li>Skype for Business で利用できない Teams の機能を活用する</li>
<li>Office 365 内で機能強化された最新のワークプレース</li>
<li>ユーザーの柔軟性の向上</li>
<li>すべての機能を一度に有効化できる</li>
</ul></td>
<td align="left"><ul><li>Skype for Business で利用できない Teams の機能を活用する</li>
<li>Office 365 内で機能強化された最新のワークプレース</li>
<li>ユーザーの生産性への影響を最小限に抑える</li>
<li>機能の重複を削減する</li>
<li>UC シナリオにおける最適なツール選択</li>
<li>組織で必要に応じて機能を有効化できるように IT およびビジネスを強化する</li>
<li>ユーザーのために変更のペースを制御する</li></ul></td>
</tr>
<tr class="odd">
<td align="left"><strong>考慮事項</strong></td>
<td align="left"><ul>
<li>同様の重複する機能を持つ複数のアプリ</li>
<li>サポート コールの増加、存在感のない IT、生産性への影響の増大といった問題につながるユーザーの困惑を引き起こす可能性の増加</li>
<li>ネットワーク計画および監視では 2 つのサービスの使用を考慮する必要がある</li>
<li>即座に行う必要のある変更管理の取り組み (啓発、トレーニング、サポート) の増大</li>
<li>ユーザーがアプリ間の相互運用に関する制限に直面する可能性</li>
</ul></td>
<td align="left"><ul><li>IT がライセンスからユーザー エクスペリエンスまで細かい制御を行うため、計画と実装において追加のサイクルが必要になる</li>
<li>Teams の選択機能を無効にするために必要なユーザーの指導とアクション</li>
<li>Teams の選択機能を無効にするために必要な変更管理の取り組み</li>
<li>ネットワーク計画および監視では 2 つのサービスの使用を考慮する必要がある</li>
<li>ユーザーがアプリ間の相互運用に関する制限に直面する可能性</li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a>管理下にない共存での移行
---------------------------------------


![管理下にない共存での移行の図。](media/guidance_SkypeforBusiness_image4.png)

管理下にない共存での移行では、Teams はコラボレーション ソリューション (チャットベースのワークスペース、チャネル、アプリ、その他の Office 365 ワークロードとの統合など) として導入されます。この場合、デスクトップ コンピューター (PC または Mac) やモバイル デバイスでのクライアント ソフトウェアや Web クライアントを使用することになります。


既定では、Teams にはプライベートのチャットと通話、予約済み会議など、Skype for Business と重複する機能も存在します。 これは、Teams が組織に完全な通信/コラボレーション ソリューションを提供するということであると同時に、Skype for Business にも同様な機能が存在することを意味します。

Teams は Skype for Business Online ユーザーとの相互運用性をサポートするため、ユーザーは Teams を起動するときに好みのチャット アプリや通話アプリを選択できます。 ユーザーが好みのアプリとして Teams を選択し、別のユーザーが Teams をインストールしておらず Skype for Business を好みのチャット/通話 アプリとして選択した場合でも、Teams に搭載される相互運用性を介してお互いにチャットや通話を行うことができます。

Microsoft は相互運用のエクスペリエンスを継続的に向上させています。 初期の段階では、相互運用のエクスペリエンスがユーザーの期待に応えていないケースが存在した可能性もあります。 ユーザーは現在でも Skype for Business を利用できるため、Skype for Business に切り替えて Teams によって提供されていない機能を補完することができます。

重複するもう 1 つの機能に Teams の予約済み会議があります。この機能では、ユーザーは Teams 会議または Skype for Business 会議のいずれかを予約できます。 これらのソリューションにはそれぞれの利点がありますが、Teams の会議エクスペリエンスがビジネス要件に適合するもので、Skype for Business 会議の機能を超えるようになると、ユーザーは自然と Teams 会議に移行することが予測されます。

管理下にない共存での移行では、相互運用の機能に関する問題に直面するユーザーからのサポート コールを処理するため、ヘルプデスク チームを用意する必要があります。 または、Teams 会議または Skype for Business 会議のどちらを優先すべきかユーザーにアドバイスを提供します。

共存でのこの移行は組織規模で適用可能であり、ユーザーは管理下にない共存のエクスペリエンスの特質を受け入れる立場にあります。したがって、組織はユーザーの要件に合う最適な通信/コラボレーション ツールを選択することを率直に受け入れることになります。

<a name="managed-side-by-side-customer-journey"></a>管理下にある共存での移行
-------------------------------------

![管理下にある共存での移行の図。](media/guidance_SkypeforBusiness_image2.png)

Teams の導入に対する制御を強めたい組織では、管理下にある共存での移行を開始します。

-   この移行の**最初のステップ**では、最新のコラボレーション要件 (チャットベースのワークスペース、チャネル、アプリ、その他の Office 365 ワークロードとの統合など) に範囲を絞った Teams の制限付きパイロットを実施します。 Teams で臨時のチャネル会議やプライベート チャットも有効にして、パイロット ユーザーに Teams 会議とプライベート チャットのエクスペリエンスを評価する機会を与えます。 この段階では、Teams の予約済み会議とプライベート通話機能は無効にしておきます。 パイロットを開始するには、「[Pilot Teams with Skype for Business (Skype for Business と共存する Teams のパイロット)](pilot-essentials.md)」をご覧ください。
    
-   導入の **2 番目のステップ**では、組織全体でプライベート チャットによる最新のコラボレーションに向けて Teams のロールアウトを拡張します。 Skype for Business 機能との重複を回避するため、Teams で予約済み会議とプライベート通話を継続して無効のままにします。

    この段階では、組織全体で優先するチャット アプリケーションを Teams または Skype for Business のいずれかに設定するかを考慮しなければならない場合があります。

    - Teams に設定する場合は、組織内の他の部門や組織全体で通信を行う場合に直面する相互運用の課題に初期の段階で対処できるようユーザーを指導する必要があります。
    
    - Skype for Business に設定する場合でも、Teams 内でのプライベート チャットは Teams 内で実行されます。エンドユーザーは Teams 内でそのチャット機能が備えるクロスプラットフォームの特長をすぐに活用できます。同時に、ユーザーは組織内または組織全体の Skype for Business ユーザー同士のプライベート チャットにこれまでどおり Skype for Business を使用できます。


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>注意</p></td>
<td align="left"><br><br>現時点では、チャット アプリケーションの優先設定はクライアント レベルでのみ利用できます。 意図した組織全体にわたる構成を促進するためにユーザー トレーニングや導入キャンペーンを行う必要があります。</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

管理下にある共存での移行の **3 番目のステップ**は、組織が Teams の会議エクスペリエンスと機能が組織のビジネス要件に適合すると判断した時点で開始します。 Teams のプライベート会議とチャネル会議を有効にすると、ユーザーは Teams 会議と Skype for Business 会議の両方を予約することができるオプションを利用できます。 したがって、Teams の継続的な革新性を考慮すれば、時間の経過とともにユーザーは Teams 会議に移行することが予測されます。 Skype for Business から Teams への使用の切り替えを円滑に促すために、Teams を使い始めるに際しての明瞭なガイダンスを利用して Teams がユーザーに提供する付加価値を説明する、トレーニング、サポート、コミュニケーションを含む強力な変更管理プログラムを実施します。 啓発キャンペーンの設計に役立つ [User Readiness (ユーザーの準備状況)](http://aka.ms/UserReadiness) リソースをご利用いただけます。


管理下にある共存での移行の **4 番目のステップ**では Teams の通話機能を有効にします。 このステップでは、シームレスな共存エクスペリエンスを確実にするために Teams の相互運用機能を重視します。 プライベート通話に Teams を使用することを推進するには、Teams を既定の通信アプリとして設定することが理想的です。 

時間の経過とともに、通信およびコラボレーションの要件を満たすために、組織全体で Teams だけに依存するようになり、**5 番目のステップ**に進むことが予測されます。 Teams に新機能が導入される時期については、「[Office 365 Roadmap (Office 365 ロードマップ)](http://aka.ms/TeamsRoadmap)」をご覧ください。 

<a name="managing-side-by-side-experience"></a>共存エクスペリエンスの管理
--------------------------------

既定では、資格のある Office 365 サブスクリプションを保有している組織では、Microsoft Teams が有効化されます。 組織が管理下にない共存での移行の条件に適合する場合は、現状を維持して Microsoft Teams の導入を自然な流れで促すことをお勧めします。

Teams は、IT 管理権限が不要な最新の Web ブラウザー デスクトップ クライアント (インストール時。現時点では PC にのみ適用可能) やモバイル クライアントからアクセスできます。

プライベートなチャットや通話から、臨時会議や予約済み会議、およびアプリまで、Teams のすべての機能は既定で有効になります。そのため、ユーザーはニーズに合わせて機能を試したり使用したりすることができます。 Teams の初回実行時のエクスペリエンスにより、ユーザーは好みのチャット/通話アプリケーション (Microsoft Teams または Skype for Business) を選ぶことができます。

Teams などの新しいツールのリリースを組織でより積極的に制御する場合は、管理下の共存での移行について次のオプションを考慮することができます。

-   コラボレーションに向けた Teams のパイロットおよびロールアウト 「[Pilot Teams with Skype for Business (Skype for Business と共存する Teams のパイロット)](pilot-essentials.md)」をご覧ください。

-   会議に向けた Teams のロールアウト

-   通話に向けた Teams のロールアウト

### <a name="teams-pilot-and-rollout-for-collaboration"></a>コラボレーションに向けた Teams のパイロットとロールアウト

Microsoft Teams は、Office 365 グループの機能強化を通して、Office 365 との統合と常設チャットを基礎として構築されています。

既定では、資格のある Office 365 サブスクリプション ライセンスを有する組織内のユーザーは Teams に対して有効になるため、制限付きの Teams パイロットはパイロット グループ外のすべてのユーザーの Teams ライセンスを無効にすることに関係します。

コラボレーションとプライベート チャットのソリューションとしての Teams のリリースに焦点をあてて、Skype for Business と機能が重複していることによるユーザーの混乱を軽減するには、Office 365 テナント レベルで次の設定を変更することができます。 Office 365 設定を変更するには、「[Office 365 を使用する組織で Microsoft Teams をセットアップする](Office-365-set-up.md)」をご覧ください。

<table>
<thead>
<tr class="header">
<th align="left">セクション</th>
<th align="left">設定</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>通話と会議</strong></td>
<td align="left"><p>プライベート会議の予約を許可する: <strong>オフ</strong></p><p>チャネル会議の予約を許可する: <strong>オフ</strong></p><p>プライベート通話を許可: <strong>オフ</strong></p></td>
<td align="left"><p>この設定を無効にすると、ユーザーはプライベート会議を予約できなくなります。</p><p>この設定を無効にすると、ユーザーはチャネル会議を予約できなくなります。</p><p>この設定を無効にすると、ユーザーはプライベート通話 (音声およびビデオ) を行うことができなくなります。</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>注意</p></td>
<td align="left"><br><br>Business ユーザーと Enterprise ユーザーの両方でプライベート通話を無効にする必要があります。組織でゲスト アクセスが適用可能な場合はゲスト ユーザーのプライベート通話も無効にする必要があります。</td>
</tr>
</thead>
<tbody>
</tbody>
</table>



この構成では、最新のコラボレーション エクスペリエンスの一部として、臨時のチャネル会議の使用を促進し、音声、ビデオ、画面共有の使用を有効にすることで、Teams の会議の仕組みをユーザーに紹介することができます。 エンドユーザーは Teams のクロスプラットフォームの常設プライベート チャット機能も利用できます。

コラボレーションおよびプライベート チャットに向けた Teams のパイロットが成功したら、その次にすべてのユーザーに対して Teams ライセンスを有効にして組織全体で広範なロールアウトを実施できます。

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>注意</p></td>
<td align="left">パイロットの実施時、およびプライベート チャットが有効な段階 2 では、Skype for Business ユーザーとの Teams ユーザーのチャットで次の操作を行うことができません。<br>
- チャット セッションからビデオ通話を開始する<br>
- ファイルを転送する <br>
- チャット セッションから複数パーティ間の通話を開始する<br>
- ユーザーはデスクトップ共有セッションを開始できない<br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a>会議に向けた Teams のロールアウト

ユーザーが Microsoft Teams を使用したコラボレーションに慣れてきたら、次に有効にする機能として予約済み会議を検討します。

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>注意</p></td>
<td align="left"><br><br>予約済み会議の開催者には、Exchange Online マルチテナント (または Exchange Online 専用 vNext) でのメールボックスが必要です。</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

テナントレベルで次の設定を構成して、Teams で予約済み会議を有効にします。これらの設定は Business および Enterprise ユーザーにのみ適用されます。

<table>
<thead>
<tr class="header">
<th align="left">セクション</th>
<th align="left">設定</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>通話と会議</strong></td>
<td align="left"><p>プライベート会議の予約を許可する: <strong>オン</strong></p><p>チャネル会議の予約を許可する: <strong>オン</strong></p></td>
<td align="left"><p>この設定を有効にすると、ユーザーはプライベート会議を予約できようになります。</p><p>この設定を有効にすると、ユーザーはチャネル会議を予約できるようになります。</p></td>
</tr>
</tbody>
</table>


予約済み会議は、Teams デスクトップ クライアントやブラウザー、または Microsoft Teams の会議アドインを使用した Microsoft Outlook で開催できます。 Teams で予約済み会議を有効にすると同時に、ユーザーに対して新しい Teams 会議の作成、既存の Skype for Business から Teams 会議への更新についての指導を開始することをお勧めします。

### <a name="rollout-of-teams-for-calling"></a>通話に向けた Teams のロールアウト

Teams のプライベート通話の機能は、Skype for Business に取って代わる強力な機能として継続して開発されます。 Teams のプライベート通話機能が主要なビジネス要件に適合すると組織が判断した場合は、Teams のプライベート通話を有効にするために次の設定をテナントレベルで構成することができます。 

<table>
<thead>
<tr class="header">
<th align="left">セクション</th>
<th align="left">設定</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>通話と会議</strong></td>
<td align="left"><p>Allow private calling (プライベート通話を許可): <strong>オン</strong></p></td>
<td align="left"><p>この設定を有効にすると、ユーザーはプライベート通話 (音声およびビデオ) を行うことができます。</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>注意</p></td>
<td align="left"><br><br>Allow users to chat privately (ユーザーがプライベートでチャットすることを許可する): この設定を有効にすると、ユーザーは他のユーザーとプライベートでチャットすることができるようになります。</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


この段階では、優先する通話アプリとして Teams を選択するようにすべてのユーザーに指導します。

プライベート通話を有効にすることで、Skype for Business が提供するすべての機能が Teams で利用可能になり、ユーザーは通信とコラボレーションの要件を完全に満たすソリューションとして Teams の使用を開始できます。


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><strong>次のアクション:</strong> Skype for Business と共存する Teams を稼動状態にしたら、[ユーザーによる Teams の導入を介してその価値を創出](continue-journey.md)すると同時に Skype for Business から Teams への移行を継続的に実施します。</td>
</tr>
</thead>
<tbody>
</tbody>
</table>