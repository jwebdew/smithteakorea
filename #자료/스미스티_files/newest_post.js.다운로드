var NEWEST_POST = function(){

	var mode;

	var getReviewUrl = function(type,prod_url,idx){
		if(type == 'shop_review'){
			location.href = prod_url+'#prod_detail_review!/'+idx;
		}else{
			location.href = prod_url+'#prod_detail_qna!/'+idx;
		}
	};

	//bmode 구해서 변수에 셋팅
	var setParameterByName = function(name){
		name = name.replace(/[\[]/, "\\[").replace(/[\]]/, "\\]");

		var regex = new RegExp("[\\?&]" + name + "=([^&#]*)"),
			results = regex.exec(location.search);

		mode = null === results ? "" : decodeURIComponent(results[1].replace(/\+/g, " "))
	};

	var newestClickLike = function(post_code, like_token_key, like_token){
		event.stopPropagation();

		if(mode === 'view'){ //게시글 본문과 같은 페이지에 있으면 갱신버튼을 본문 좋아요 버튼으로 셋팅
			post_like_reaction.init('post', post_code, $('#view_like_btn_' + post_code), $('#view_like_count_' + post_code));
		}else{
			post_like_reaction.init('post', post_code, $('#like_btn_' + post_code), $('#like_count_' + post_code));
		}
		post_like_reaction.checkLikeToken(like_token_key, like_token, post_code);
		post_like_reaction.toggleLike();
	};

	return {
		getReviewUrl : function(type,prod_url,idx){
			return getReviewUrl(type,prod_url,idx);
		},

		setParameterByName : function(name){
			setParameterByName(name);
		},

		newestClickLike : function(post_code, like_token_key, like_token){
			newestClickLike(post_code, like_token_key, like_token);
		}
	}
}();