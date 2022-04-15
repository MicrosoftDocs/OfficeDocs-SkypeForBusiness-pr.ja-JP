---
title: Microsoft Teams の Reflect への IT 管理者ガイド
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams for Education の Reflect への IT 管理者ガイドです。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d17409a09cbadc535e3b7971d6224b4e2fcb678b
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839038"
---
# <a name="it-admin-guide-to-reflect-in-microsoft-teams"></a>Microsoft Teams の Reflect への IT 管理者ガイド

このドキュメントでは、[Microsoft Teams の Education Insights](class-insights.md) に不可欠な要素である [Reflect](https://aka.ms/reflect) に関する情報を提供します。 Reflect は、学生が自分の感情を認識し、コントロールできるようにするために、共有や傾聴の機会を定期的に提供するためのサポートをします。 Reflect は、学習者の感情表現に必要な語彙を増やし、仲間に対する共感を深めると同時に、教室の健全なコミュニティを維持するために教師に貴重なフィードバックを提供します。

このチェックイン アプリは、絵文字や研究に裏付けられた感情についての精度を用いて、教師の忙しい日常業務への社会性や感情に関する学びの場の追加をサポートします。


## <a name="privacy-and-security"></a>プライバシーとセキュリティ
Reflect は、[Education Insights](class-insights.md) と同じプライバシーとセキュリティ標準に従って学生の機密情報を保護します。

Microsoft 365 の一部として、Reflect は、[GDPR](/compliance/regulatory/gdpr) や学生の教育記録のプライバシーを保護する[学生と子供のセキュリティに関する家族教育権およびプライバシー法 (FERPA)](/compliance/regulatory/offering-ferpa) など、データの収集と使用に関する国、地域、業界固有の規制を満たしています。

データは教育機関に属し、Microsoft はデータを収集して保存するだけです。 Microsoft の担当者は、データ リカバリなど、サービスを維持するための監査された方法でコンプライアンスによって許可されている場合を除き、データにアクセスしたり、データを表示したりすることはできません。

学生が他の学生の名前を閲覧することは *なく*、反応の内容のみが表示されます。 回答の分布を確認することはできますが、それぞれの反応に関連付けられている名前を表示することは *できません*。 

> [!NOTE]
> 学生による回答が 5 人に満たない場合には、学生にデータは表示されません。 これは、学生同士がお互いの回答を識別してしまう可能性を最小限にするための措置です。

> [!TIP]
> * [Microsoft トラストセンターの](https://www.microsoft.com/trust-center) にアクセスして、Microsoft でデータを保護している方法をご確認ください。
> * [Microsoft コンプライアンス オファリング](/compliance/regulatory/offering-home)にアクセスして、Microsoft 365 がお客様の機関で規制コンプライアンス基準を満たすためにどのような役割を果たすかご確認ください。

## <a name="data-collection-and-storage"></a>データの収集と記憶域
データは教育機関に属しており、Microsoft が行うのはデータの収集と保存のみです。 Microsoft の担当者は、データ リカバリなど、サービスを維持するための監査された方法でコンプライアンスによって許可されている場合を除き、データにアクセスしたり、データを表示したりすることはできません。

データは Education Insights に保存されます。 既定では、Education Insights はオンになっています。 オプトアウトすると、Reflect 用に収集された **すべてのデータが削除されます**。 Education Insights をオンに戻すと、データが再度有効になった時点からデータの収集が開始されます。

「[Education Insights への IT 管理者ガイド](class-insights.md)」では、Education Insights の仕組み (保存場所など) や、データを削除したり、サービスを有効にしたりする際に [Education Insights をオフまたはオンにする方法](class-insights.md#turn-insights-on-or-off)について説明しています。

Reflect では学生からデータを収集しますが、ゲスト データは収集されません。 **学生がゲストとして定義されている場合には、そのユーザーのデータは収集されません。** 

## <a name="enable-reflect"></a>Reflect を有効にする
教育機関のアプリ設定ポリシーを管理する場合は、Reflect がテナントで *許可* されていることをご確認ください。 また、Teams 管理センターから Reflect を関連するクラスのチームに追加することもできます。

ユーザーが任意のアプリをインストールして操作できるようにするには、**[アプリの管理]** ページからアプリを組織レベルで許可し、ユーザーに割り当てられている **アプリのアクセス許可ポリシー** を許可する必要があります。

各アプリに許可が必要となるように事前に定義している場合には、[アプリの管理] ページから Reflect を "許可" してください。 **アプリをブロックすると、組織内のすべてユーザーに対してそのアプリが Teams に表示されなくなります。**

> [!NOTE]
> Reflect アプリにアクセスするには、Microsoft 365 の A1、A3、A5 ライセンスが必要です。

> [!TIP]
> 詳細については、「[How to allow an app or to add it to a class team (アプリを許可するか、クラスのチームに追加する方法)](manage-apps.md#allow-and-block-apps)」を参照してください。

## <a name="where-do-educators-find-reflect"></a>Reflect はどこから利用できますか?
Reflect を有効にしたら教師はクラスに移動し、**[新しい会話]** を選択します。 そして、**[...]** を選択してメッセージング拡張機能を表示し、検索バーに 「**Reflect**」と入力します。 ダイアログ ボックスでは、質問や、誰が何を表示できるかに関する定義をガイドします。

:::image type="content" source="media/reflect-add-app.png" alt-text="クラス チームに Reflect を追加します。":::

[Reflect] アイコンを右クリックして **[固定]** を選択することにより、アクセスが簡単になります。

:::image type="content" source="media/reflect-pin-app.png" alt-text="Reflect アプリを固定します。":::

> [!TIP]
> このリンクから Reflect アプリを見つけることもできます。[https://aka.ms/getReflect](https://aka.ms/getReflect)

> [!TIP]
> 詳細については、「[Reflect サポート ページ](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a)」を参照してください。このページでは、教師と学生の両方に関するガイドラインを提供し、最初のリフレクション チェックインを作成する方法について説明します。
