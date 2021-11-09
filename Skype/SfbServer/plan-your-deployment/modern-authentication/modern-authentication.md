---
title: '[最新の認証を計画する] Skype for Business'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 他の製品との統合を含む、Skype for Business Server認証と承認のトピックを計画する
ms.openlocfilehash: 3bcd9ab78c9703dd938230740fddba4034aff315
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851871"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>認証と認証について説明する (Skype for Business

認証と承認は関連する概念ですが、作業は異なります (両方とも必要です)。 簡単に言いますと、Authenciation (AuthN) は、有効なユーザーだけが知っている、または持っているシークレットに依存します。パスワード、コード、指紋、証明書、ユーザーに関するクレームの組み合わせ、またはこれらが組み合わせて使用されます。 AuthN は、自分が自分であることを証明するプロセスです。

承認 (AuthZ) は、自分が誰かを証明した後にアクセスできる情報に関係します。 表示、編集、その他のアクセスが許可されている内容が決定されます。 たとえば、SharePoint Online に強力なサイト コレクション管理者アクセス権を持つ場合がありますが、Skype for Business Online など、別のオンライン ワークロードに切り替える場合は、サーバーやサーバーの構成を変更するのではなく、ユーザーの問題をトラブルシューティングする権限を持っている可能性があります。 3 番目のワークロード (Exchange Onlineなど) では、平均ユーザーのアクセス権しか持てない場合があります。 AuthZ は、サービス/worloads、アプリケーション、ファイル、その他のデータに対するアクセス権とアクセス量をチェックします。

この例では、SharePoint や Exchange online などのオンライン プロパティが含まれますが、AuthN と AuthZ のプロセスはオンプレミスとハイブリッド施設で同じように動作します。 最終的には、AAD Connect や ADFS などのツールは、オンプレミスのアカウントとパスワードをクラウドの AD (Azure AD) に同期するか、AuthZ のフローに侵入して、ユーザーが資格情報を頻繁に要求されなかった場合など、クラウド内のワークロードを切り替えてシングル Sign-On シナリオを作成することで、AuthN および AuthZ ストーリーに関与します。 しかし、それ自体では、責任ある AuthN や AuthZ ではなく、メカニズムの一部にすら含まれています。

今日、多くのテクノロジでは、これらのプロセス (AuthN と AuthZ) を 1 つのメカニズムと見なしています。また、認証プロセスへの参照も多数聞こえます。 ユーザー アクセスの最初の手順は AuthN であり、自分が誰だと言うのか、AuthZ はユーザーがアクセスできるユーザーの知識を使用して (Open Authorization または OAuth を参照してください) ことを覚えておく必要があります。

  
## <a name="authentication-and-authorization-planning-topics"></a>認証と承認の計画に関するトピック

[モダン認証 (ADAL) とパスワードを使用するSkype for Business](plan-adal.md)

[先進認証でサポートされている Skype for Business トポロジ](topologies-supported.md)

[従来の認証方法をネットワークに対して内部および外部でオフにする計画。](turn-on-modern-auth.md)

