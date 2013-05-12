angular.module('CouchDB', ['ngResource']).
    factory('ProjectCouch', function($resource) {
        var ProjectCouch = $resource(':protocol//:server/:db/:q/:r/:s/:t',
                                     {protocol: 'http:', server: 'localhost:5984', db: 'projects'}, {update: {method:'PUT'}   
                               }
       ); 

       ProjectCouch.prototype.update = function(cb) {
        return ProjectCouch.update({q: this._id},
            this, cb);
      };

      ProjectCouch.prototype.destroy = function(cb) {
          return ProjectCouch.remove({q: this._id, rev: this._rev}, cb);
      };

      return ProjectCouch;
    });
