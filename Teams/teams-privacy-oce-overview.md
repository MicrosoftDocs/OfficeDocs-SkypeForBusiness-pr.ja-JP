---
title: Teamsのオプションの接続エクスペリエンス
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: ''
ms.localizationpriority: high
search.appverid: MET150
description: この記事では、Microsoft Teams に表示されるオプションの接続エクスペリエンスについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03c23ccc1e9d24733f083c3e1d780b38138d366e
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396268"
---
# <a name="overview-of-optional-connected-experiences-in-microsoft-teams"></a>Microsoft Teamsでのオプションの接続エクスペリエンスについての概要

職場または学校のアカウントがある場合、組織の管理者は、Microsoft Teamsを使用しているときにGIPHY および/またはURL プレビューサービスのように、(**オプションの接続エクスペリエンス** とも呼ばれている)1つや２つ以上のクラウドベースのサービスを提供されているかもしれません。 これらのクラウド バックアップ サービスは、任意で利用できます。 利用するかどうかは、あなた次第です。 これらは、オプション サービスごとに個別に説明されているように、 [Microsoft Online サービス条項](https://www.microsoft.com/licensing/product-licensing/products)とは異なる条件で提供されます。 この記事ではTeamsのクラウドベースのサービスについて説明します。

管理者が Teams でオプションの接続エクスペリエンスを使用する機能を付与している場合は、Teams の **[設定]** > **[プライバシー]** に移動して、オプションの接続エクスペリエンスを使用するかどうかを選択できます。

> [!NOTE]
> 管理者の場合、ユーザーがオプションの接続エクスペリエンスを使用できるようにしたり、制限したりできます。 これを行うには、[Office クラウド ポリシー サービス](/deployoffice/overview-office-cloud-policy-service)を使用し、*Office での追加オプションである接続エクスペリエンスの使用を許可する* ポリシー設定を構成します。 これは、Microsoft 365 Apps for enterprise に含まれる Office アプリ (Word、Excel、PowerPoint など) でユーザーがオプションの接続エクスペリエンスを利用できるかどうかを制御するのと同じポリシー設定です。

## <a name="giphy"></a>GIPHY

GIPHY は、Teamsのチャットで GIFを使用できる、クラウドベースのサービスです。 **Teams** > **GIF** > **Search** を使用している場合は、検索語句が GIPHY に送信されます。 管理者によって許可された場合、および使用することを選択した後、これらの操作は、[GIPHY プライバシーポリシー](https://support.giphy.com/hc/articles/360032872931-GIPHY-Privacy-Policy)と[サービス使用条件](https://support.giphy.com/hc/articles/360020027752-GIPHY-User-Terms-of-Service)の対象となります。

:::image type="content" source="media/giphy-menu.png" alt-text="これは Giphy 選択ボタンと、Giphy の画像を取得するために、情報を入力するテキストボックスを表示するメニューです。":::

## <a name="url-preview-service"></a>URL プレビューサービス

Url プレビューサービスでは、ユーザーが URL 文字列を送信すると、自動的にプレビュースニペットが生成され、このスニペットの下に表示されます。 このサービスは、ユーザーがメッセージを入力しているときにサービス URL に要求を送ります。 サービス URL に schema.org データがない場合は、プレビュー スニペットを生成するために必要なデータを取得するために、検索Bing要求を送信します。 Bingに依存するエクスペリエンスは、 [Microsoft Services 契約](https://www.microsoft.com/servicesagreement) の条項に基づいてライセンスが付与され、 [プライバシーに関する声明](https://privacy.microsoft.com/privacystatement)の対象となります。 これらのサービスを使用しているときに Microsoft Teams に提供するすべての URL は、Microsoft Bingに送信できます。 これらは、Bing組織によってリンクされません。

:::image type="content" source="media/url-preview.png" alt-text="Microsoft ホームページ用の URL プレビューのサンプルをテキストボックスに表示する画面。":::

## <a name="teams-apps-link-previews"></a>Teams アプリのリンク プレビュー

Teams アプリ リンク プレビュー サービスは、アプリのアダプティブ カードのプレビュー スニペットを生成し、ユーザーが Teams ストア内のアプリにマップする URL 文字列を送信したときに URL の下に添付します。 このサービスは、ユーザーがメッセージを入力しているときにサービス URL に要求を送ります。

## <a name="teams-device-store-checkout"></a>Teams デバイス ストアのチェックアウト  

Teams デバイス ストアは Teams 管理センターにあり、Teams 認定デバイスの検出と購入が可能です。 チェックアウトを有効にするために、Teams デバイス ストアは、ユーザーの電子メール アドレス、ユーザー GUID、テナント GUID などの基本的なユーザーと会社の情報を UnifiedCommunications.com と共有します。 このエクスペリエンスは、[**Office ポリシーで追加のオプションの接続エクスペリエンスの使用を許可** する] ポリシー設定で許可されている場合、UnifiedCommunications.com の利用規約とプライバシーに関する声明の対象となります。 

:::image type="content" source="media/teams-device-store-buttons.png" alt-text="Teams 管理センターからデバイスを購入できるサードパーティの会社である UnifiedCommunications.com によって提供されるチェックアウト オプションを含む Teams デバイス ストア ページの一部のスクリーンショット。":::

Teams デバイス ストアの詳細については、「:[Teams デバイス ストアでデバイスを購入する」を](devices/device-store.md)参照してください。

## <a name="related-articles"></a>関連記事

- [Teamsのポリシーコントロールの概要](policy-control-overview.md)
- [プライバシーと Microsoft Teams](teams-privacy.md)
- [Office でのオプションの接続エクスペリエンスについての概要](/deployoffice/privacy/optional-connected-experiences)
- [Office の必要なサービス データ](/deployoffice/privacy/required-service-data)
- [アカウント プライバシーの設定](https://support.microsoft.com/office/3e7bc183-bf52-4fd0-8e6b-78978f7f121b)
