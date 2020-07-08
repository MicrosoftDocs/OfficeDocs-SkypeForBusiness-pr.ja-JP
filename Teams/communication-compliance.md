---
title: Microsoft Teams の通信のコンプライアンス
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: コミュニケーションのコンプライアンスについては、「Microsoft Teams の観点からの insider リスクソリューションセットの一部 (M365 通信のコンプライアンス機能の一部)」をご覧ください。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf97f4adc33b0855e986cf2baed54f69de91f4f0
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077695"
---
# <a name="communication-compliance-for-microsoft-teams"></a>Microsoft Teams の通信のコンプライアンス

通信のコンプライアンスは、Microsoft 365 で強化された新しい insider リスクソリューションの一部であり、組織内の不適切なメッセージに対する修復措置を検出、キャプチャし、解決するのに役立ちます。 チームチャネルまたは1:1 やグループチャットで不快感を持たせたり、嫌がらせをしたりすることができます。 また、ポリシーを設定して、機密情報がチームチャネルまたは1:1 とグループチャットの一部として共有されているかどうかを確認することもできます。 さまざまな種類のポリシーとその設定方法の詳細については、 [「M365 の記事](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)を参照してください。

## <a name="how-to-use-communication-compliance-in-teams"></a>Teams で通信のコンプライアンスを使用する方法

### <a name="identify-inappropriate-messages"></a>不適切なメッセージを特定する

Microsoft Teams で送信されたメッセージ (1:1、グループチャット、またはチャネルの会話) を特定したい場合は、ポリシーを有効にして確認することができます。また、レビュー担当者は、メッセージを確認して、トレーニング資料を送信したり、適切な措置をとるなどの必要な手順を実行することができます。

### <a name="identify-sensitive-or-regulatory-information"></a>機密情報または規制情報を特定する

Microsoft Teams (1:1、グループチャット、またはチャネルでの会話) で送信されたメッセージを、機密情報や規制の種類に対してスキャンする場合は、事前に定義された機密または規制の種類をサポートするポリシーを選ぶことができます。

> [!NOTE]
> プライベートチャネルは、通信のコンプライアンスによってサポートされていません。

### <a name="custom-policy"></a>カスタムポリシー

このテンプレートを使用して、特定の通信チャネル、個々の検出条件、組織内で監視およびレビューするコンテンツの量を構成します。

### <a name="custom-trainable-classifier"></a>Custom Trainable クラシファイア

Box 分類子のいずれかが目的に合わない場合は、trainable 分類子を使います。 Microsoft 365 分類子は、さまざまな種類のコンテンツを認識できるようにトレーニングするためのツールです。 分類子のトレーニングでは、最初に、ユーザーが選択してカテゴリに対してプラスのサンプルを提供する必要があります。 次に、これらのサンプルを処理した後、正と負の標本の組み合わせを指定して予測をテストします。 詳細については、このトピックの詳細については、 [M365 の記事](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier)を参照してください。

> [!NOTE]
> 通信コンプライアンスが Exchange ハイブリッド展開をサポートするようになりました。

通信のコンプライアンスは、ポリシーに一致するすべてのメッセージの会話履歴をサポートします。 これにより、調査管理者にコンテキストが提供されます。

:::image type="content" source="media/communication-compliance-1.png" alt-text="Microsoft Teams での通信のコンプライアンスのための画面。":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a>チームで通信ポリシーを適用できる場所

通信コンプライアンスポリシーをセットアップして、Teams で送信されたメッセージを次のレベルで設定することができます。

- ユーザーレベル: 管理者は、個々のユーザーレベルでポリシーを設定したり、テナントのすべてのユーザーに適用したりすることができます。 これは、ユーザーが1:1 またはグループチャットで送信したメッセージのみを対象とします。
- チームレベル: 管理者は、チームでポリシーを設定することもできます。 これにより、そのチームのチャネルで送信されたすべてのメッセージ (プライベートチャネルメッセージはサポートされません) が対象となります。
