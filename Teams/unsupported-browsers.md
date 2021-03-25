---
title: サポートされていないブラウザーでの Microsoft Teams 会議
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: サポートされていないブラウザーでの Teams でのオーディオとビデオのサポートについて学習します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83617628fe04140c45b005e993d95eac34c6f8bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121315"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>サポートされていないブラウザーでの Microsoft Teams 会議

Internet Explorer 11、Safari、Firefox などの一部のブラウザーは Microsoft Teams Web アプリをサポートしていますが、Teams の通話および会議機能の一部はサポートされていません。 この制限を回避するために、Teams Web アプリを使用すると、ユーザーは PSTN 接続を介して音声を受信し、表示されたコンテンツ (画面共有) を表示速度を低下して表示できます。

> [!Note]
> Microsoft 365 のアプリとサービスは、2021 年 8 月 17 日から Internet Explorer 11 をサポートしない予定です (Microsoft Teams では、2020 年 11 月 30 日から Internet Explorer 11 以前はサポートされていません)。 [詳細情報を参照してください](https://aka.ms/AA97tsw)。 Internet Explorer 11 は、サポート対象のブラウザーとして残ることに注意してください。 Internet Explorer 11 は Windows オペレーティング システムのコンポーネントであり[](/lifecycle/faq/internet-explorer-microsoft-edge)、インストールされている製品のライフサイクル ポリシーに従います。

Teams がサポートされていないブラウザーを検出すると、問題とセッションの制限を説明するメッセージが自動的に表示されます。 このメッセージには、Teams がユーザーに通話を呼び出せするように呼び出し元の番号を残すようユーザーに指示したり、会議出席依頼に含まれる電話会議番号に電話するようにユーザーに指示したりなど、会議の音声にアクセスする手順が示されます。 このメッセージでは、Teams デスクトップ クライアントをダウンロードして [使用し、Teams](https://teams.microsoft.com/downloads) の完全なエクスペリエンスを得る方法もユーザーに推奨されます。

PSTN が利用できない場合、ユーザーには会議にアクセスする手順が表示され、会議に参加できません。

## <a name="browser-limitations"></a>ブラウザーの制限事項

サポートされていないブラウザーで Teams Web アプリを使用するユーザーには、次の制限があります。

- 音声は PSTN 接続でのみ利用できます。 ユーザーは自分のマイクを使用することはできません。
- ユーザーはカメラを共有したり、他の参加者のビデオを表示したりできないが、画像ベースの画面共有を通じて表示されたコンテンツを表示できる。
- ユーザーは自分の画面を共有できないが、別の会議参加者が共有している画面を表示できる。
- ユーザーは、画面共有セッション中に制御を受け取る必要があります。
- ユーザーは着信通話通知を受信しない。
- 通話が中断された場合、会議は自動的に再接続されません。
- ユーザーが会議を開始できない。

Teams でのブラウザー サポートの詳細については、「Teams の制限と [仕様」を参照してください](./limits-specifications-teams.md#browsers)。

## <a name="related-topics"></a>関連項目

- [サポートされていないブラウザーで Teams 会議に参加する](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)