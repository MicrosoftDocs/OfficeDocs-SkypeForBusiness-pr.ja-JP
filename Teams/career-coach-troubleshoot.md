---
title: Microsoft Teams のキャリア コーチのトラブルシューティング
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams の Career Coach で一般的な問題のトラブルシューティングを行う方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5ebda4324f7cc46d69b882a53684b21b4fa2932
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024172"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Microsoft Teams のキャリア コーチのトラブルシューティング

この記事は、Microsoft Teams の Career Coach のトラブルシューティングを行う必要がある、教育機関の IT 管理者向けです。

IT 管理者が Career Coach で実行できる一般的な問題と解決手順を次に示します。

## <a name="missing-required-configuration-data"></a>必要な構成データがありません

Career Coach エクスペリエンスで "Career Coach は現在すぐに使用できるようにセットアップされています" と表示 **される場合、必要なすべての構成データは追加されていません**。

Career Coach **を使用するには、次のセクションを完了する必要があります** 。

- [ブランドと設定](career-coach-set-up-steps.md#brand-and-preferences)
- [LinkedIn 接続](career-coach-set-up-steps.md#linkedin-connection)
- [コース カタログ](career-coach-set-up-steps.md#course-catalog)
- [研究分野](career-coach-set-up-steps.md#fields-of-study)

[キャリア コーチの構成状態](career-coach-set-up-steps.md#configuration-status)を参照して、完了する必要がある設定を確認します。

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>コース カタログまたは調査データのフィールドの書式設定が正しくありません

コース カタログと専門分野の CV には、必要な形式と最大サイズが 18 MB です。

適切な構成を確保するために、[学習ドキュメント スキーマの](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) Career Coach [コース カタログ ドキュメント スキーマ](career-coach-set-up-steps.md#course-catalog-document-format-and-schema)と Career Coach フィールドを参照してください。

また、正常な処理を確実に行うために、コース カタログ ファイルに 15,000 行を超えてはなりません。

## <a name="missing-fields-in-career-coach-settings-pages"></a>キャリア コーチ設定ページのフィールドが見つからない

[キャリア コーチの設定] ページには必須フィールドがあります。 必要なフィールドが入力されていない場合、ページは送信されません。

警告メッセージが表示されず、ページが送信されない場合があります。

ページの上部に緑色のバナーが表示されると、送信は成功します。

## <a name="setup-policy-changes-arent-complete"></a>セットアップ ポリシーの変更が完了していない

ユーザー向けの Microsoft Teams に Career Coach が表示されていない場合は、セットアップ ポリシーの変更がまだ有効になっていない可能性があります。 セットアップ ポリシーの変更が有効になるまで、Career Coach は Microsoft Teams のユーザーに対してインストールおよびピン留めされません。 ポリシーの変更が有効になるには数時間かかる場合があります。

ただし、Career Coach は、Microsoft Teams アプリ ストアから直接インストールできます。

- ユーザーが Microsoft Teams アプリ ストアで Career Coach を見つけることができない場合は、アプリのアクセス許可ポリシーを確認し、Career Coach がブロックされたアプリではないことを確認します。
- Career Coach は Microsoft アプリであり、アクセス許可ポリシーによって Microsoft アプリを許可することをお勧めします。 [アクセス許可ポリシーの構成](teams-app-permission-policies.md)の詳細について説明します。

## <a name="career-coach-initialization-isnt-complete"></a>キャリア コーチの初期化が完了していない

次のエラーが発生する可能性があります。"アプリの設定を取得できません。 もう一度お試しください。 引き続き問題が発生する場合は、Microsoft カスタマー サポートにお問い合わせください。

[[キャリア コーチの設定] ページ](career-coach-set-up-steps.md#career-coach-settings-status)で **サービス プロビジョニングの状態** を確認します。

テナントがまだ初期化されている場合は、15 分待ってからもう一度試してください。 それでもエラーが発生した場合は、サポート チケットを開きます。
