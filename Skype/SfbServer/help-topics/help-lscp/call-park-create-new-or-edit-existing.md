---
title: Call Park Create New or Edit Existing
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: 呼び出しパーク番号の範囲は、パークされた通話が保持される一時的な番号を定義します。その番号は、他のユーザーが通話を取得するか、または時間が切れるまで保持されます。
ms.openlocfilehash: c8d489c75516357193ca1bc4f3ae6f4d613bd80d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760965"
---
# <a name="call-park-create-new-or-edit-existing"></a>コール パーク: 新規作成または現在の形式のままで編集

呼び出しパーク番号の範囲は、パークされた通話が保持される一時的な番号を定義します。その番号は、他のユーザーが通話を取得するか、または時間が切れるまで保持されます。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのフィールドを示します。

- **名前** 番号範囲を識別するわかりやすい名前を入力します。 番号範囲を保存した後、この名前を変更することはできません。

- **数値範囲** 最初のフィールドに、番号範囲の先頭番号を入力します。 2 番目のフィールドに、数値範囲の終了番号を入力します。

  - 範囲の開始番号が終了番号より大きくならないようにしてください。

  - 範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。

  - 番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。

  - 数値範囲が文字または #で始まる場合、範囲は 100 より大きい必要 \* があります。

  - 有効な値: 正規表現文字列と一致する必要があります ([ \\ *|#]?1-9]\d {0,7} )|([1-9]\d)。 {0,8} つまり、値は、文字または # で始まる文字列か、1 ~ 9 の数値である必要があります (最初の文字は \* 0 にすることはできません)。 最初の文字が #の場合、次の文字は 1 ~ 9 の数値 \* である必要があります (ゼロにすることはできません)。 後続の文字には、任意の数字 0 ~ 9 の追加文字 \* ("#6000"、"92000"、"95551212"、および "915551212" など) を指定 \* できます。 最初の文字がまたは #ではない場合、最初の文字は 1 から 9 の数字 (ゼロにすることはできません) で、その後に最大 8 文字、それぞれ 0 ~ 9 の数字 \* (たとえば、915551212;41212;300) を指定する必要があります。

  - プール当たりの番号の合計数が 50,000 件を超えないようにしてください。各番号範囲は、通常、100 以下の番号を含みますが、10,000 件を超えなければ、範囲をそれよりも広くすることができます。たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。

- **宛先サーバーの FQDN** コール パーク アプリケーションをホストする Application サービスの完全修飾ドメイン名 (FQDN) またはサービス ID を選択します。 番号範囲内の開始番号と終了番号で指定された範囲内の番号に対してパークされているすべての呼び出しは、このサーバーまたはプールにルーティングされます。

コール パークの機能の詳細については[、「Plan for Call Park in Skype for Business 2015」を参照](../../plan-your-deployment/enterprise-voice-solution/call-park.md)してください。 コール パーク番号範囲の操作の詳細については[、「Configure 電話番号拡張機能」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)。