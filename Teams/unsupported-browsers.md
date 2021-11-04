---
title: Microsoft Teamsブラウザーで会議を行う
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: サポートされていないブラウザー Teamsオーディオとビデオをサポートする方法について学習します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 213de938360754efd95b5fb460c0cf5a3c735203
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740143"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>Microsoft Teamsブラウザーで会議を行う

Internet Explorer 11、Safari、Firefox などの一部のブラウザーでは、Microsoft Teams Web アプリがサポートされますが、Teams 通話および会議機能の一部はサポートされていません。 この制限を回避するために、Teams Web アプリを使用すると、ユーザーは PSTN 接続を介して音声を受信し、表示されたコンテンツ (画面共有) を表示レートを低くすることができます。

> [!Note]
> Microsoft 365アプリとサービスは、2021 年 8 月 17 日から Internet Explorer 11 をサポートしない予定です (Microsoft Teams では、2020 年 11 月 30 日から Internet Explorer 11 以前はサポートされていません)。 [詳細情報を参照してください](https://aka.ms/AA97tsw)。 Internet Explorer 11 は、サポート対象のブラウザーとして残ることに注意してください。 Internet Explorer 11 は、Windows オペレーティング システムのコンポーネントであり、インストールされている[](/lifecycle/faq/internet-explorer-microsoft-edge)製品のライフサイクル ポリシーに従います。

サポートTeamsが検出されると、問題とセッションの制限を説明するメッセージが自動的に表示されます。 このメッセージでは、Teams がユーザーに通話できるよう、ユーザーにコール バック番号を残すようユーザーに指示したり、会議出席依頼に含まれる電話会議番号に電話するようにユーザーに指示したりして、会議の音声にアクセスする手順をさらに説明します。 また、このメッセージを使用すると、ユーザーはデスクトップ[](https://teams.microsoft.com/downloads)クライアントをダウンロードTeams完全なエクスペリエンスを得Teamsされます。

PSTN が利用できない場合、ユーザーは会議にアクセスする手順を表示し、会議に参加できません。

## <a name="browser-limitations"></a>ブラウザーの制限事項

サポートされていないブラウザーで Teams Web アプリを使用するユーザーには、次の制限があります。

- 音声は PSTN 接続でのみ使用できます。 ユーザーは自分のマイクを使用することはできません。
- ユーザーはカメラを共有したり、他の参加者のビデオを見たりできないが、画像ベースの画面共有を通じて表示されたコンテンツを表示できる。
- ユーザーは自分の画面を共有できないが、別の会議参加者が共有する画面を表示できる。
- ユーザーは、画面共有セッション中に制御を受け取る必要があります。
- ユーザーは着信通話通知を受け取らない。
- 通話が中断された場合、会議は自動的に再接続されません。
- ユーザーが会議を開始できない。

ブラウザーのサポートの詳細については、「Teams の制限と仕様[」を参照Teams。](./limits-specifications-teams.md#browsers)

## <a name="related-topics"></a>関連項目

- [サポートされていないブラウザー Teams会議に参加する](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)