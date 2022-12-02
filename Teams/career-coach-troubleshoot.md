---
title: Microsoft Teams のキャリア コーチのトラブルシューティング
author: DaniEASmith
ms.author: danismith
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams のキャリア コーチで一般的な問題のトラブルシューティングを行う方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c00837c40fe405ab4d9d608326a12567843c8bb
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242451"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Microsoft Teams のキャリア コーチのトラブルシューティング

この記事は、Microsoft Teams のキャリア コーチのトラブルシューティングを行う必要がある教育 IT 管理者向けです。

以下に、IT 管理者がキャリア コーチに対して実行する可能性がある一般的な問題と解決策の手順を示します。

## <a name="missing-required-configuration-data"></a>必要な構成データがありません

キャリア コーチ エクスペリエンスに 「キャリア コーチは現在、すぐに使用できるように設定されています」と表示 **されている場合は、必要なすべての構成データが追加されていません**。

教育機関では、 [LinkedIn 接続](career-coach-set-up-steps.md#linkedin-connection-required) が完全に構成されている必要があります。

[キャリア コーチの構成状態](career-coach-set-up-steps.md#configuration-status)を参照して、完了する必要がある設定を確認します。

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>コース カタログまたは学習フィールド データの書式が正しくありません

コース カタログと研究分野の CV には、必要な形式と最大サイズが 18 MB です。

適切な構成を確保するために、キャリア コーチ [コースカタログドキュメントスキーマ](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) と [キャリアコーチフィールドの学習ドキュメントスキーマ](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) を参照してください。

また、正常な処理を確実に行うために、コース カタログ ファイルに 15,000 行を超えてはなりません。

## <a name="missing-fields-in-career-coach-settings-pages"></a>キャリア コーチの設定ページのフィールドがありません

キャリア コーチの設定ページには必須フィールドがあります。 必要なフィールドが完了していない場合、ページは送信されません。

警告メッセージが表示されず、ページが送信されない場合があります。

送信は、ページの上部に緑色のバナーが表示されると成功します。

## <a name="setup-policy-changes-arent-complete"></a>セットアップ ポリシーの変更が完了しない

ユーザーの Teams Microsoftにキャリア コーチが表示されない場合は、セットアップ ポリシーの変更がまだ有効になっていない可能性があります。 セットアップ ポリシーの変更が有効になるまで、Microsoft Teams のユーザーに対してキャリア コーチはインストールおよびピン留めされません。 ポリシーの変更が有効になるまでに数時間かかることがあります。

ただし、キャリア コーチは、Microsoft Teams アプリ ストアから直接インストールできます。

- ユーザーがMicrosoft Teams アプリ ストアでキャリア コーチを見つけることができない場合は、アプリのアクセス許可ポリシーを確認し、キャリア コーチがブロックされたアプリではないことを確認します。
- キャリア コーチはMicrosoft アプリであり、アクセス許可ポリシーでアプリMicrosoft許可することをお勧めします。 [アクセス許可ポリシーの構成](teams-app-permission-policies.md)の詳細については、こちらをご覧ください。

## <a name="career-coach-initialization-isnt-complete"></a>キャリア コーチの初期化が完了していない

"アプリの設定を取得できません。 もう一度お試しください。 問題が引き続き発生する場合は、カスタマー サポートMicrosoft問い合わせてください。

[キャリア コーチの設定ページ](career-coach-set-up-steps.md#career-coach-settings-status)で **、サービス プロビジョニングの状態** を確認します。

テナントがまだ初期化されている場合は、15 分待ってからやり直してください。 それでもエラーが発生する場合は、サポート チケットを開きます。
