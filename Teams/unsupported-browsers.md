---
title: サポートされていないブラウザーでの Microsoft Teams 会議
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: nakulm
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: サポートされていないブラウザーで Teams がオーディオとビデオをサポートする方法について説明します。
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 71fb02fae88f2f61d2d6435e126e20093a5a3baf
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267828"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>サポートされていないブラウザーでの Microsoft Teams 会議

Internet Explorer 11、Safari、Firefox などの一部のブラウザーでは、Microsoft Teams Web アプリがサポートされていますが、Teams の通話機能や会議機能の一部はサポートされていません。 この制限を回避するために、Teams Web アプリを使用すると、ユーザーは PSTN 接続を介してオーディオを受信し、表示速度を下げ、表示されるコンテンツ (画面共有) を表示できます。

> [!Note]
> Microsoft 365 アプリとサービスは、2021 年 8 月 17 日から Internet Explorer 11 をサポートしません (Microsoft Teams では、2020 年 11 月 30 日より前の Internet Explorer 11 はサポートされません)。 [詳細情報を参照してください](https://aka.ms/AA97tsw)。 Internet Explorer 11 は、サポート対象のブラウザーとして残ることに注意してください。 Internet Explorer 11 は Windows オペレーティング システムのコンポーネントであり、インストールされている製品 [のライフサイクル ポリシーに従います](/lifecycle/faq/internet-explorer-microsoft-edge) 。

Teams がサポートされていないブラウザーを検出すると、問題とセッションの制限事項を説明するメッセージが自動的に表示されます。 このメッセージには、Teams がユーザーを呼び出すことができるようにコールバック番号を残すようにユーザーにアドバイスしたり、会議出席依頼に含まれる電話会議番号を呼び出すようにユーザーに指示したりするなど、会議の音声にアクセスするための詳細な手順が示されます。 また、このメッセージでは、Teams [デスクトップ クライアント](https://teams.microsoft.com/downloads) を完全な Teams エクスペリエンスにダウンロードして使用することをお勧めします。

PSTN が利用できない場合、ユーザーは会議にアクセスするための手順を表示せず、会議に参加できません。

## <a name="browser-limitations"></a>ブラウザーの制限事項

サポートされていないブラウザーで Teams Web アプリを使用するユーザーには、次の制限事項が発生します。

- 音声は PSTN 接続でのみ使用できます。 ユーザーは自分のマイクを使用できません。
- ユーザーはカメラを共有したり、他の参加者のビデオを見たりすることはできませんが、画像ベースの画面共有を通じて表示されたコンテンツを表示できます。
- ユーザーは自分の画面を共有できませんが、別の会議参加者が共有する画面が表示されます。
- ユーザーは画面共有セッション中に制御を取ることはできません。
- ユーザーは着信通知を受け取りません。
- 通話が中断された場合、会議は自動的に再接続されません。
- ユーザーは会議を開始できません。

Teams でのブラウザーのサポートの詳細については、「 [Teams の制限と仕様」を参照してください](./limits-specifications-teams.md#browsers)。

## <a name="related-topics"></a>関連項目

- [サポートされていないブラウザーで Teams 会議に参加する](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)