# assignment-2

## The following functions cache and compute the inverse of a matrix

## This function creates a special "matrix" object that can cache 
## its inverse

makeCacheMatrix <- function(x = matrix()) {
	inverse <- NULL
	set <- function (x) {
		mtx <<- x;
		inverse << - NULL;
	}
	
	get <- function() return(mtx);
	setinv <- function(inv) inverse <<- inv;
	getinv <- function() return (inverse);
	return (list (set = set, get = get, setinv = setinv, getinv = getinv))

}


## This function computes the inverse of the special "matrix" returned 
## by 'makeCacheMatrix'. If the inverse has already been calculated
## (and the matrix has not changed), then 'cacheSolve' should retrieve 
## the inverse from the cache.

cacheSolve <- function(x, ...) {
        inverse <- mtx$getinv()
        if(!id.null(inverse)) {
        	message ("Getting cached data...")
        	return (inverse)
        }
        data <- mtx$get()
        inverse <- solve(data, ...)
        mtx$setinv (inverse)
        return (inverse)
}
