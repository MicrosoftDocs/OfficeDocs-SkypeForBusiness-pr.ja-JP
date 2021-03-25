---
title: 管理センターで小売業向けの Teams テンプレートを使用する
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 管理センターを使用して定義済みの設定、チャネル、および事前にインストールされたアプリを提供することで、小売業者のニーズに合わせて設計されたチーム構造を作成する Teams テンプレートの使用方法を説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a63602f07e0c248b4decbc733e41b16fdafc3911
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117615"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a>管理センターで小売業向けの Teams テンプレートを使用する

Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。

Teams テンプレートには、小売業者のニーズに基づいて設計されたチーム構造の定義が事前に作成されています。 Teams テンプレートを使用すると、小売業者にとって適切なチームの種類をすばやく作成し、組織全体に展開できます。 Teams テンプレートを拡張して、組織固有のニーズに合わせてチームを作成することもできます。

この記事では、各 Teams テンプレートと、それらの使用を推奨する方法について説明します。

この記事は、小売業の組織全体で複数のチームを計画、展開し、管理する責任があるユーザーに役立ちます。 組織内に Teams サービスがすでに展開されていることを前提としています。 展開がまだの場合は、「[Microsoft Teams の展開方法](./deploy-overview.md)」をお読みになって展開を開始してください。

一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。

## <a name="organize-a-store"></a>店舗を整理する

小売業の従業員を 1 つのエクスペリエンスにまとめ、タスクの管理、ドキュメントの共有、およびお客様の問題の解決を行います。 追加のアプリケーションを統合して、シフトの開始と終了のプロセスを合理化します。

| 基本テンプレートの種類 |baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------|-- |----------------------------------------------------- |
|店舗を整理する|`retailStore`|チャネル: <ul><li>全般<li>シフトのハンドオフ</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li></ul>|
||||

## <a name="manager-collaboration"></a>マネージャー コラボレーション

マネージャー コラボレーションのテンプレートは、マネージャーのグループが店舗や地域間でコラボレーションするためのチームを作成する場合などに最適です。たとえば、組織に地域別のグループがある場合、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域のすべての店舗マネージャーと、その地域の地域マネージャーを含めることができます。

| 基本テンプレートの種類| baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------|- |----------------------------------------------------- |
|小売業 - マネージャー コラボレーション|`retailManagerCollaboration` |チャネル: <ul><li>全般<li>操作</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li></ul>|
||||