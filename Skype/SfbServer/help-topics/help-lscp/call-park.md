---
title: コール パーク
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: 通話がパークされた場合、通話は一時的な番号に転送され、誰かが通話を取得するか、または通話がタイム アウトするまで保持されます。パークされた通話のために予約する内線番号の範囲を含むテーブルを構成する必要があります。 これらの内線番号は仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要あがります。 コール パーク アプリケーションを実行する各プールは、1 つ以上の内線番号の範囲を持つ場合があります。 これらの範囲は、展開全体でグローバルに一意である必要があります。
ms.openlocfilehash: 7723b3bb3145725834059c73c0acc273fc67ca61
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800307"
---
# <a name="call-park"></a>コール パーク

通話がパークされた場合、通話は一時的な番号に転送され、誰かが通話を取得するか、または通話がタイム アウトするまで保持されます。パークされた通話のために予約する内線番号の範囲を含むテーブルを構成する必要があります。 これらの内線番号は仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要あがります。 コール パーク アプリケーションを実行する各プールは、1 つ以上の内線番号の範囲を持つ場合があります。 これらの範囲は、展開全体でグローバルに一意である必要があります。

[ **コール パーク]** ページには、組織に対して定義されているコール パーク番号の範囲の一覧が表示されます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**コール パーク**] ページでは次のタスクを実行できます。

- 新しい番号範囲の作成

- 既存の番号範囲の変更

- 番号範囲の削除

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのコマンドを示します。

- **新規** 新しいコール パーク番号範囲を開始します。

- **編集** 選択した番号範囲を編集用に開き、リスト内のすべての番号範囲を選択するか、選択した番号範囲を削除します。

- **更新** 番号範囲の一覧を更新します。

次の一覧に、このページのフィールドを示します。

- **名前** 番号範囲を識別する一意の名前。

- **開始範囲** 範囲の開始番号を指定します。

- **終了範囲** 範囲の終了番号を指定します。

- **Destination** 番号範囲のコール パーク アプリケーションをホストするアプリケーション サービスの完全修飾ドメイン名 (FQDN) またはサービス ID。

コール パークの機能の詳細については [、「Plan for Call Park in Skype for Business 2015」](../../plan-your-deployment/enterprise-voice-solution/call-park.md)を参照してください。 コール パーク番号範囲の操作の詳細については [、「Configure Phone Number Extensions for Parking Calls 」を参照してください](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。


