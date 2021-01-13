---
title: Plan for Modern Authentication in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 他の製品との統合を含む、Skype for Business Server の認証と承認の計画に関するトピック
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816247"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Skype for Business での認証と承認について

認証と承認は関連する概念ですが、作業は異なります (両方とも必要です)。 簡単に言うなら、認証 (AuthN) は、有効なユーザーだけが知っている、または持っているシークレットに依存します。パスワード、コード、指紋、証明書、ユーザーに関するクレームの組み合わせ、またはこれらが組み合わせて使用される場合があります。 AuthN は、自分が自分の言い分であることを証明するプロセスです。

承認 (AuthZ) は、自分が誰かを証明した後にアクセスできる情報に関係します。 表示、編集、その他のアクセスが許可されている内容が決定されます。 たとえば、SharePoint Online への強力なサイト コレクション管理者アクセス権を持っている場合でも、Skype for Business Online など別のオンライン ワークロードに切り替える場合は、サーバーの構成を変更するのではなく、ユーザーの問題をトラブルシューティングする権限を持っている可能性があります。 Exchange Online などの 3 番目のワークロードでは、平均的なユーザーのアクセス権しか持てない場合があります。 AuthZ は、サービス/worloads、アプリケーション、ファイル、その他のデータに対して持っているアクセスの量と量を確認します。

この例では、SharePoint や Exchange Online などのオンライン プロパティが含まれますが、AuthN と AuthZ のプロセスはオンプレミスとハイブリッドのオンプレミスで同じように動作します。 最終的には、AAD Connect や ADFS などのツールは、オンプレミスのアカウントとパスワードをクラウドの AD (Azure AD) に同期するか、AuthZ のフローに侵入してユーザーに資格情報の入力を頻繁に求めなかったりすることで、AuthN や AuthZ のストーリーに関与します。たとえば、クラウド内のワークロードを切り替える際に、単一の Sign-On シナリオを作成します。 ただし、このメカニズムの一部として、それ自体が責任を持つ AuthN や AuthZ というのではない。

現在、多くのテクノロジでは、これらのプロセス (AuthN と AuthZ) が 1 つのメカニズムと見なされ、認証プロセスへの多くの参照が聞こえます。認証プロセスには承認も含まれます。 ユーザー アクセスの最初のステップは AuthN であり、ユーザーが誰かの知識を使用してユーザーがアクセス権を持っているユーザーを判断します (Open Authorization または OAuth で確認できます)。

  
## <a name="authentication-and-authorization-planning-topics"></a>認証と承認の計画に関するトピック

[Skype for Business でモダン認証 (ADAL) を使用する方法](plan-adal.md)

[先進認証でサポートされている Skype for Business トポロジ](topologies-supported.md)

[ネットワークの内部および外部で従来の認証方法をオフにする計画。](turn-on-modern-auth.md)

