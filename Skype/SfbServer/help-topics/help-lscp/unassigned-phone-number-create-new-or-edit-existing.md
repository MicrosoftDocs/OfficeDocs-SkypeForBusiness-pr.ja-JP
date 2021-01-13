---
title: 割り当てられていない電話番号の作成、または既存の番号の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: 未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。
ms.openlocfilehash: 741068fc16c60e6cd253057a8b1487680dc32266
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818797"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>割り当てられていない電話番号: 新規作成または現在の形式のままで編集

未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。

> [!IMPORTANT]
> 新しい未使用の番号範囲の作成または既存の未使用の番号範囲の編集が終了して [**OK**] をクリックすると、[**未使用の番号**] ページに戻り、すべての番号範囲が表示されます。[**新規 未使用の番号範囲**] ページまたは [**編集 未使用の番号範囲**] ページで行った変更は、[**未使用の番号**] ページで [**すべてコミット**] をクリックするまでは、データベースにコミットされません。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのフィールドを示します。

- **名前** 割り当てられていない番号範囲を識別するわかりやすい名前を入力します。 範囲を保存した後、この名前を変更することはできません。

- **番号の範囲** 最初のフィールドに、割り当てられていない番号範囲の開始番号を入力します。 2 番目のフィールドに、範囲の終了番号を入力します。

  - 範囲の開始番号が終了番号より大きくならないようにしてください。

  - 範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。

  - The number must match the regular expression (tel:)?( \+ )?[1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?. つまり、番号は tel: (文字列を指定しない場合は自動的に追加されます)、プラス記号 (+)、および 1 ~ 9 の数字で始まる可能性があります。 電話番号は最大 17 桁で、その後に内線番号 ;ext= の後に内線番号を続けることもできます。

- **アナウンス サービス** アナウンス **アプリケーションで** 着信呼び出しを処理する場合は [アナウンス] を選択し、 **着信** 呼び出しを処理する Exchange UM 自動応答 Exchange UM を使用します。

- [**アナウンス サービス**] で [**アナウンス**] を選択した場合:

  - **送信先サーバーの FQDN** この割り当てられていない番号範囲への着信呼び出しを処理するアナウンス アプリケーションを実行するアプリケーション サービスのサービス ID を選択します。

  - **アナウンス** この割り当てられていない番号の範囲で再生するアナウンスを選択します。

- [**アナウンス サービス**] で [**Exchange UM**] を選択した場合:

  - **自動応答電話番号** Exchange UM メールボックスの電話番号を自動応答。

アナウンスの機能の詳細については、「計画」のドキュメントの [「Plan for the Announcement application in Skype for Business 2015」](../../plan-your-deployment/enterprise-voice-solution/announcement.md) を参照してください。 未使用の番号範囲の操作の詳細については、「操作」のドキュメントの「[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)」を参照してください。


