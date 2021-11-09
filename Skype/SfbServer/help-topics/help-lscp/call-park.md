---
title: コール パーク
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: 呼び出しがパークされている場合、通話は一時的な番号に転送され、呼び出しは誰かが呼び出しを取得するか、または時間が切れるまで保持されます。パークされた呼び出しのために予約する内線番号の範囲を持つテーブルを構成する必要があります。 これらの内線番号は仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要あがります。 コール パーク アプリケーションを実行する各プールには、1 つ以上の範囲の拡張機能を使用できます。 これらの範囲は、展開全体でグローバルに一意である必要があります。
ms.openlocfilehash: 14c5ddbf3bd7f2d862cfd3f3e89310932964b8b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841569"
---
# <a name="call-park"></a>コール パーク

呼び出しがパークされている場合、通話は一時的な番号に転送され、呼び出しは誰かが呼び出しを取得するか、または時間が切れるまで保持されます。パークされた呼び出しのために予約する内線番号の範囲を持つテーブルを構成する必要があります。 これらの内線番号は仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要あがります。 コール パーク アプリケーションを実行する各プールには、1 つ以上の範囲の拡張機能を使用できます。 これらの範囲は、展開全体でグローバルに一意である必要があります。

[ **コール パーク]** ページには、組織に対して定義されているすべての通話パーク番号範囲の一覧が表示されます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**コール パーク**] ページでは次のタスクを実行できます。

- 新しい番号範囲の作成

- 既存の番号範囲の変更

- 番号範囲の削除

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのコマンドを示します。

- **New** 新しい通話パーク番号範囲を開始します。

- **編集** 選択した番号範囲を編集用に開き、リスト内のすべての番号範囲を選択するか、選択した番号範囲を削除します。

- **更新** 番号範囲の一覧を更新します。

次の一覧に、このページのフィールドを示します。

- **名前** 番号範囲を識別する一意の名前。

- **開始範囲** 範囲の開始番号。

- **終了範囲** 範囲の終了番号。

- **宛先** 番号範囲のコール パーク アプリケーションをホストする Application サービスの完全修飾ドメイン名 (FQDN) またはサービス ID。

コール パークの機能の詳細については[、「Plan for Call Park in Skype for Business 2015」を参照](../../plan-your-deployment/enterprise-voice-solution/call-park.md)してください。 コール パーク番号範囲の操作の詳細については[、「Configure 電話番号拡張機能」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)。