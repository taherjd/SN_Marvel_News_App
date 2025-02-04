# SN_Marvel_News_App
var MarvelNewsAPI = Class.create();
MarvelNewsAPI.prototype = {
    initialize: function() {},

    getLatestNews: function() {
        var request = new sn_ws.RESTMessageV2();
        request.setEndpoint('https://newsapi.org/v2/everything?q=Marvel%20Movies&apiKey=YOUR_NEWSAPI_KEY');
        request.setHttpMethod('GET');

        var response = request.execute();
        var responseBody = response.getBody();
        var parsedResponse = JSON.parse(responseBody);

        return parsedResponse.articles || [];
    },

    type: 'MarvelNewsAPI'
};
